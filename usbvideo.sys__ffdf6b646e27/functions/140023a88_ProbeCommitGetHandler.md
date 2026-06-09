# ProbeCommitGetHandler

- ea: `0x140023a88`
- end: `0x140023c67`
- name: `ProbeCommitGetHandler`
- size: `479`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002b5a0`
- `0x14002b7f0`
- `0x14002ba30`
- `0x14002bc80`

## callees

- `0x140009dc8`
- `0x14001b15c`
- `0x140023a88`
- `0x140040a30`
- `0x140040a70`
- `0x140040b40`

## import_xrefs

- `ks!KsGetFilterFromIrp` at `0x140023ac5`
- `ks!KsGetFilterFromIrp` at `0x140023ac5`
- `ks!KsGetDevice` at `0x140023b3f`
- `ks!KsGetDevice` at `0x140023b3f`

## pseudocode

```c
__int64 __fastcall ProbeCommitGetHandler(IRP *a1, unsigned int a2, _OWORD *a3)
{
  __int64 v3; // rdi
  unsigned int SetInterfaceControl; // ebx
  PKSFILTER FilterFromIrp; // rax
  _QWORD *Context; // r9
  __int64 v8; // rdi
  int v9; // edx
  PKSDEVICE Device; // rsi
  int v11; // r8d
  int v12; // r9d
  __int64 result; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  int v16; // eax
  int v17; // r9d
  int v18; // r8d
  int v19; // edx
  int v20; // edx
  int v21; // r8d
  int v22; // r9d
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-48h]
  SIZE_T NumberOfBytesa; // [rsp+28h] [rbp-48h]
  __int64 v27; // [rsp+30h] [rbp-40h] BYREF
  __int128 Src; // [rsp+38h] [rbp-38h] BYREF
  __int128 v29; // [rsp+48h] [rbp-28h]
  __int128 v30; // [rsp+58h] [rbp-18h]

  v3 = a2;
  Src = 0;
  SetInterfaceControl = -1073741823;
  v29 = 0;
  v27 = 0;
  v30 = 0;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  if ( !FilterFromIrp )
    return SetInterfaceControl;
  if ( (unsigned int)v3 < FilterFromIrp->Descriptor->PinDescriptorsCount )
  {
    Context = FilterFromIrp->Context;
    _mm_lfence();
    v8 = *(_QWORD *)(Context[8] + 8 * v3);
    if ( !v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids, Context);
      return SetInterfaceControl;
    }
    Device = KsGetDevice(FilterFromIrp);
    if ( Device )
    {
      if ( *(_DWORD *)(v8 + 104) )
      {
        LOBYTE(v12) = *(_BYTE *)(v8 + 177);
        LOBYTE(v11) = 2;
        LODWORD(NumberOfBytes) = *(_DWORD *)(v8 + 180);
        LOBYTE(v9) = -127;
        result = GetSetInterfaceControl((int)Device, v9, v11, v12, &Src, NumberOfBytes);
        if ( (int)result < 0 )
          return result;
        SetInterfaceControl = 0;
      }
      else
      {
        memmove(&Src, (const void *)(v8 + 184), *(unsigned int *)(v8 + 180));
        v14 = *(_QWORD *)(v8 + 16);
        v15 = *(_QWORD *)(v8 + 392);
        WORD1(Src) = *(_WORD *)(v14 + 76);
        v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v15 + 104LL))(
                v15,
                0,
                v14 + 96,
                &v27);
        LOBYTE(v17) = *(_BYTE *)(v8 + 177);
        LOBYTE(v18) = 1;
        DWORD1(Src) = v16;
        LOBYTE(v19) = 1;
        LODWORD(NumberOfBytes) = *(_DWORD *)(v8 + 180);
        SetInterfaceControl = GetSetInterfaceControl((int)Device, v19, v18, v17, &Src, NumberOfBytes);
        if ( (SetInterfaceControl & 0x80000000) != 0 )
          return SetInterfaceControl;
        LOBYTE(v21) = 1;
        LOBYTE(v22) = *(_BYTE *)(v8 + 177);
        LOBYTE(v20) = -127;
        LODWORD(NumberOfBytesa) = *(_DWORD *)(v8 + 180);
        SetInterfaceControl = GetSetInterfaceControl((int)Device, v20, v21, v22, &Src, NumberOfBytesa);
        if ( (SetInterfaceControl & 0x80000000) != 0 )
          return SetInterfaceControl;
      }
      v23 = v29;
      *a3 = Src;
      v24 = v30;
      a3[1] = v23;
      a3[2] = v24;
    }
  }
  else
  {
    return (unsigned int)-1073741811;
  }
  return SetInterfaceControl;
}

```

## disassembly

```asm
0x140023a88  push    rbp
0x140023a8a  push    rbx
0x140023a8b  push    rsi
0x140023a8c  push    rdi
0x140023a8d  push    r14
0x140023a8f  mov     rbp, rsp
0x140023a92  sub     rsp, 70h
0x140023a96  mov     rax, cs:__security_cookie
0x140023a9d  xor     rax, rsp
0x140023aa0  mov     [rbp+var_8], rax
0x140023aa4  xorps   xmm0, xmm0
0x140023aa7  mov     edi, edx
0x140023aa9  movups  [rbp+var_38], xmm0
0x140023aad  mov     r14, r8
0x140023ab0  mov     ebx, 0C0000001h
0x140023ab5  movups  [rbp+var_28], xmm0
0x140023ab9  mov     [rbp+var_40], 0
0x140023ac1  movups  [rbp+var_18], xmm0
0x140023ac5  call    cs:__imp_KsGetFilterFromIrp
0x140023acc  nop     dword ptr [rax+rax+00h]
0x140023ad1  mov     rdx, rax
0x140023ad4  test    rax, rax
0x140023ad7  jz      loc_140023C4D
0x140023add  mov     rax, [rax]
0x140023ae0  cmp     edi, [rax+20h]
0x140023ae3  jb      short loc_140023AEF
0x140023ae5  mov     ebx, 0C000000Dh
0x140023aea  jmp     loc_140023C4D
0x140023aef  mov     r9, [rdx+10h]
0x140023af3  lfence
0x140023af6  mov     rax, [r9+40h]
0x140023afa  mov     rdi, [rax+rdi*8]
0x140023afe  test    rdi, rdi
0x140023b01  jnz     short loc_140023B3C
0x140023b03  mov     rcx, cs:WPP_GLOBAL_Control
0x140023b0a  lea     rax, WPP_GLOBAL_Control
0x140023b11  cmp     rcx, rax
0x140023b14  jz      loc_140023C4D
0x140023b1a  cmp     byte ptr [rcx+29h], 3
0x140023b1e  jb      loc_140023C4D
0x140023b24  mov     rcx, [rcx+18h]
0x140023b28  lea     edx, [rdi+13h]
0x140023b2b  lea     r8, WPP_6541fcaf218a315b5bab6f01f1c99150_Traceguids
0x140023b32  call    WPP_SF_q
0x140023b37  jmp     loc_140023C4D
0x140023b3c  mov     rcx, rdx; Object
0x140023b3f  call    cs:__imp_KsGetDevice
0x140023b46  nop     dword ptr [rax+rax+00h]
0x140023b4b  mov     rsi, rax
0x140023b4e  test    rax, rax
0x140023b51  jz      loc_140023C4D
0x140023b57  cmp     dword ptr [rdi+68h], 0
0x140023b5b  mov     eax, [rdi+0B4h]
0x140023b61  jz      short loc_140023B93
0x140023b63  mov     r9b, [rdi+0B1h]; int
0x140023b6a  mov     r8b, 2; int
0x140023b6d  mov     dword ptr [rsp+70h+NumberOfBytes], eax; NumberOfBytes
0x140023b71  mov     dl, 81h; int
0x140023b73  lea     rax, [rbp+var_38]
0x140023b77  mov     rcx, rsi; int
0x140023b7a  mov     [rsp+70h+Src], rax; Src
0x140023b7f  call    GetSetInterfaceControl
0x140023b84  test    eax, eax
0x140023b86  js      loc_140023C4F
0x140023b8c  xor     ebx, ebx
0x140023b8e  jmp     loc_140023C33
0x140023b93  mov     r8, rax; Size
0x140023b96  lea     rdx, [rdi+0B8h]; Src
0x140023b9d  lea     rcx, [rbp+var_38]; void *
0x140023ba1  call    memmove
0x140023ba6  mov     r8, [rdi+10h]
0x140023baa  lea     r9, [rbp+var_40]
0x140023bae  mov     rcx, [rdi+188h]
0x140023bb5  xor     edx, edx
0x140023bb7  mov     al, [r8+4Ch]
0x140023bbb  mov     byte ptr [rbp+var_38+2], al
0x140023bbe  mov     al, [r8+4Dh]
0x140023bc2  add     r8, 60h ; '`'
0x140023bc6  mov     byte ptr [rbp+var_38+3], al
0x140023bc9  mov     rax, [rcx]
0x140023bcc  mov     rax, [rax+68h]
0x140023bd0  call    _guard_dispatch_icall
0x140023bd5  mov     r9b, [rdi+0B1h]; int
0x140023bdc  mov     r8b, 1; int
0x140023bdf  mov     dword ptr [rbp+var_38+4], eax
0x140023be2  mov     dl, r8b; int
0x140023be5  mov     eax, [rdi+0B4h]
0x140023beb  mov     rcx, rsi; int
0x140023bee  mov     dword ptr [rsp+70h+NumberOfBytes], eax; NumberOfBytes
0x140023bf2  lea     rax, [rbp+var_38]
0x140023bf6  mov     [rsp+70h+Src], rax; Src
0x140023bfb  call    GetSetInterfaceControl
0x140023c00  mov     ebx, eax
0x140023c02  test    eax, eax
0x140023c04  js      short loc_140023C4D
0x140023c06  mov     eax, [rdi+0B4h]
0x140023c0c  mov     r8b, 1; int
0x140023c0f  mov     r9b, [rdi+0B1h]; int
0x140023c16  mov     dl, 81h; int
0x140023c18  mov     dword ptr [rsp+70h+NumberOfBytes], eax; NumberOfBytes
0x140023c1c  mov     rcx, rsi; int
0x140023c1f  lea     rax, [rbp+var_38]
0x140023c23  mov     [rsp+70h+Src], rax; Src
0x140023c28  call    GetSetInterfaceControl
0x140023c2d  mov     ebx, eax
0x140023c2f  test    eax, eax
0x140023c31  js      short loc_140023C4D
0x140023c33  movups  xmm0, [rbp+var_38]
0x140023c37  movups  xmm1, [rbp+var_28]
0x140023c3b  movups  xmmword ptr [r14], xmm0
0x140023c3f  movups  xmm0, [rbp+var_18]
0x140023c43  movups  xmmword ptr [r14+10h], xmm1
0x140023c48  movups  xmmword ptr [r14+20h], xmm0
0x140023c4d  mov     eax, ebx
0x140023c4f  mov     rcx, [rbp+var_8]
0x140023c53  xor     rcx, rsp; StackCookie
0x140023c56  call    __security_check_cookie
0x140023c5b  add     rsp, 70h
0x140023c5f  pop     r14
0x140023c61  pop     rdi
0x140023c62  pop     rsi
0x140023c63  pop     rbx
0x140023c64  pop     rbp
0x140023c65  retn
```
