# VCompGetInfoHandler

- ea: `0x14002b340`
- end: `0x14002b596`
- name: `VCompGetInfoHandler`
- size: `598`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140009dc8`
- `0x14000a468`
- `0x14001b15c`
- `0x14001b2f4`
- `0x14002b340`
- `0x140040a30`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!KeReleaseSemaphore` at `0x14002b54d`
- `ntoskrnl!KeReleaseSemaphore` at `0x14002b54d`
- `ks!KsReleaseControl` at `0x14002b55c`
- `ks!KsReleaseControl` at `0x14002b55c`
- `ks!KsAcquireControl` at `0x14002b3ad`
- `ks!KsAcquireControl` at `0x14002b3ad`
- `ks!KsGetFilterFromIrp` at `0x14002b38c`
- `ks!KsGetFilterFromIrp` at `0x14002b38c`
- `ks!KsGetDevice` at `0x14002b410`
- `ks!KsGetDevice` at `0x14002b410`

## pseudocode

```c
__int64 __fastcall VCompGetInfoHandler(IRP *a1, __int64 a2, __int64 a3)
{
  PKSFILTER FilterFromIrp; // rax
  _QWORD *p_Descriptor; // rdi
  __int64 result; // rax
  __int64 v8; // rcx
  NTSTATUS SetInterfaceControl; // ebx
  __int64 v10; // r9
  __int64 v11; // rsi
  PKSDEVICE Device; // rax
  int v13; // r14d
  __int64 Context; // r15
  __int64 VideoStreamingInputHeader; // rax
  char *v16; // r12
  __int64 v17; // r8
  __int64 v18; // rcx
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  __int64 v25; // rcx
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-58h]
  SIZE_T NumberOfBytesa; // [rsp+28h] [rbp-58h]
  char v28; // [rsp+30h] [rbp-50h] BYREF
  __int64 v29; // [rsp+38h] [rbp-48h] BYREF
  __int64 v30; // [rsp+40h] [rbp-40h]
  _OWORD Src[3]; // [rsp+48h] [rbp-38h] BYREF

  v30 = a3;
  memset(Src, 0, sizeof(Src));
  v28 = 0;
  v29 = 0;
  FilterFromIrp = KsGetFilterFromIrp(a1);
  p_Descriptor = &FilterFromIrp->Descriptor;
  if ( !FilterFromIrp )
    return 3221225473LL;
  KsAcquireControl(FilterFromIrp);
  v8 = *(unsigned int *)(a2 + 24);
  if ( (unsigned int)v8 < *(_DWORD *)(*p_Descriptor + 32LL) )
  {
    v10 = p_Descriptor[2];
    v11 = *(_QWORD *)(*(_QWORD *)(v10 + 64) + 8 * v8);
    if ( v11 )
    {
      Device = KsGetDevice(p_Descriptor);
      v13 = (int)Device;
      if ( Device )
      {
        Context = (__int64)Device->Context;
        VideoStreamingInputHeader = GetVideoStreamingInputHeader(*(unsigned int *)(a2 + 24), *(_QWORD *)(Context + 32));
        if ( VideoStreamingInputHeader )
        {
          v16 = (char *)(VideoStreamingInputHeader + 13);
          if ( !*(_BYTE *)(VideoStreamingInputHeader + 12) )
            v16 = &v28;
          v17 = *(_QWORD *)(v11 + 16);
          v18 = *(_QWORD *)(v11 + 392);
          WORD1(Src[0]) = *(_WORD *)(v17 + 76);
          DWORD1(Src[0]) = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v18 + 104LL))(
                             v18,
                             0,
                             v17 + 96,
                             &v29);
          SetInterfaceControl = AcquireProbeCommitLock(Context);
          if ( SetInterfaceControl >= 0 )
          {
            LOBYTE(v20) = 1;
            LOBYTE(v21) = *(_BYTE *)(v11 + 177);
            LOBYTE(v19) = 1;
            LODWORD(NumberOfBytes) = *(_DWORD *)(v11 + 180);
            SetInterfaceControl = GetSetInterfaceControl(v13, v19, v20, v21, Src, NumberOfBytes);
            if ( SetInterfaceControl >= 0 )
            {
              LOBYTE(v23) = 1;
              LOBYTE(v24) = *(_BYTE *)(v11 + 177);
              LOBYTE(v22) = -127;
              LODWORD(NumberOfBytesa) = *(_DWORD *)(v11 + 180);
              SetInterfaceControl = GetSetInterfaceControl(v13, v22, v23, v24, Src, NumberOfBytesa);
              if ( SetInterfaceControl >= 0 )
              {
                v25 = v30;
                *(_DWORD *)(v30 + 28) = WORD4(Src[0]);
                *(_DWORD *)(v25 + 32) = WORD5(Src[0]);
                *(_QWORD *)(v25 + 36) = 0;
                *(_DWORD *)(v25 + 44) = (4 * (*v16 & 1))
                                      | ((unsigned __int8)*v16 >> 2) & 1
                                      | (8 * (((unsigned __int8)*v16 >> 1) & 1))
                                      | (16 * (((unsigned __int8)*v16 >> 3) & 1));
              }
            }
            KeReleaseSemaphore(*(PRKSEMAPHORE *)(Context + 424), 0, 1, 0);
          }
          goto LABEL_18;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d768fed4ca1d3d5df3e949c91ce185dd_Traceguids, v10);
    }
  }
  SetInterfaceControl = -1073741823;
LABEL_18:
  KsReleaseControl(p_Descriptor);
  result = (unsigned int)SetInterfaceControl;
  a1->IoStatus.Status = SetInterfaceControl;
  return result;
}

```

## disassembly

```asm
0x14002b340  mov     [rsp-38h+arg_18], rbx
0x14002b345  push    rbp
0x14002b346  push    rsi
0x14002b347  push    rdi
0x14002b348  push    r12
0x14002b34a  push    r13
0x14002b34c  push    r14
0x14002b34e  push    r15
0x14002b350  mov     rbp, rsp
0x14002b353  sub     rsp, 80h
0x14002b35a  mov     rax, cs:__security_cookie
0x14002b361  xor     rax, rsp
0x14002b364  mov     [rbp+var_8], rax
0x14002b368  xorps   xmm0, xmm0
0x14002b36b  mov     [rbp+var_40], r8
0x14002b36f  xor     r12d, r12d
0x14002b372  mov     rbx, rdx
0x14002b375  movups  [rbp+var_38], xmm0
0x14002b379  mov     [rbp+var_50], r12b
0x14002b37d  mov     r13, rcx
0x14002b380  movups  [rbp+var_28], xmm0
0x14002b384  mov     [rbp+var_48], r12
0x14002b388  movups  [rbp+var_18], xmm0
0x14002b38c  call    cs:__imp_KsGetFilterFromIrp
0x14002b393  nop     dword ptr [rax+rax+00h]
0x14002b398  mov     rdi, rax
0x14002b39b  test    rax, rax
0x14002b39e  jnz     short loc_14002B3AA
0x14002b3a0  mov     eax, 0C0000001h
0x14002b3a5  jmp     loc_14002B56E
0x14002b3aa  mov     rcx, rdi; Object
0x14002b3ad  call    cs:__imp_KsAcquireControl
0x14002b3b4  nop     dword ptr [rax+rax+00h]
0x14002b3b9  mov     rax, [rdi]
0x14002b3bc  mov     ecx, [rbx+18h]
0x14002b3bf  cmp     ecx, [rax+20h]
0x14002b3c2  jb      short loc_14002B3CE
0x14002b3c4  mov     ebx, 0C0000001h
0x14002b3c9  jmp     loc_14002B559
0x14002b3ce  mov     r9, [rdi+10h]
0x14002b3d2  mov     rax, [r9+40h]
0x14002b3d6  mov     rsi, [rax+rcx*8]
0x14002b3da  test    rsi, rsi
0x14002b3dd  jnz     short loc_14002B40D
0x14002b3df  mov     rcx, cs:WPP_GLOBAL_Control
0x14002b3e6  lea     rax, WPP_GLOBAL_Control
0x14002b3ed  cmp     rcx, rax
0x14002b3f0  jz      short loc_14002B3C4
0x14002b3f2  cmp     byte ptr [rcx+29h], 5
0x14002b3f6  jb      short loc_14002B3C4
0x14002b3f8  mov     rcx, [rcx+18h]
0x14002b3fc  lea     edx, [rsi+11h]
0x14002b3ff  lea     r8, WPP_d768fed4ca1d3d5df3e949c91ce185dd_Traceguids
0x14002b406  call    WPP_SF_q
0x14002b40b  jmp     short loc_14002B3C4
0x14002b40d  mov     rcx, rdi; Object
0x14002b410  call    cs:__imp_KsGetDevice
0x14002b417  nop     dword ptr [rax+rax+00h]
0x14002b41c  mov     r14, rax
0x14002b41f  test    rax, rax
0x14002b422  jz      short loc_14002B3C4
0x14002b424  mov     r15, [rax+10h]
0x14002b428  mov     ecx, [rbx+18h]
0x14002b42b  mov     rdx, [r15+20h]
0x14002b42f  call    GetVideoStreamingInputHeader
0x14002b434  test    rax, rax
0x14002b437  jz      short loc_14002B3C4
0x14002b439  cmp     [rax+0Ch], r12b
0x14002b43d  lea     r12, [rax+0Dh]
0x14002b441  jnz     short loc_14002B447
0x14002b443  lea     r12, [rbp+var_50]
0x14002b447  mov     r8, [rsi+10h]
0x14002b44b  lea     r9, [rbp+var_48]
0x14002b44f  mov     rcx, [rsi+188h]
0x14002b456  xor     edx, edx
0x14002b458  mov     al, [r8+4Ch]
0x14002b45c  mov     byte ptr [rbp+var_38+2], al
0x14002b45f  mov     al, [r8+4Dh]
0x14002b463  add     r8, 60h ; '`'
0x14002b467  mov     byte ptr [rbp+var_38+3], al
0x14002b46a  mov     rax, [rcx]
0x14002b46d  mov     rax, [rax+68h]
0x14002b471  call    _guard_dispatch_icall
0x14002b476  mov     rcx, r15
0x14002b479  mov     dword ptr [rbp+var_38+4], eax
0x14002b47c  call    AcquireProbeCommitLock
0x14002b481  mov     ebx, eax
0x14002b483  test    eax, eax
0x14002b485  js      loc_14002B559
0x14002b48b  mov     eax, [rsi+0B4h]
0x14002b491  mov     r8b, 1; int
0x14002b494  mov     r9b, [rsi+0B1h]; int
0x14002b49b  mov     dl, r8b; int
0x14002b49e  mov     dword ptr [rsp+80h+NumberOfBytes], eax; NumberOfBytes
0x14002b4a2  mov     rcx, r14; int
0x14002b4a5  lea     rax, [rbp+var_38]
0x14002b4a9  mov     [rsp+80h+Src], rax; Src
0x14002b4ae  call    GetSetInterfaceControl
0x14002b4b3  mov     ebx, eax
0x14002b4b5  test    eax, eax
0x14002b4b7  js      loc_14002B53D
0x14002b4bd  mov     eax, [rsi+0B4h]
0x14002b4c3  mov     r8b, 1; int
0x14002b4c6  mov     r9b, [rsi+0B1h]; int
0x14002b4cd  mov     dl, 81h; int
0x14002b4cf  mov     dword ptr [rsp+80h+NumberOfBytes], eax; NumberOfBytes
0x14002b4d3  mov     rcx, r14; int
0x14002b4d6  lea     rax, [rbp+var_38]
0x14002b4da  mov     [rsp+80h+Src], rax; Src
0x14002b4df  call    GetSetInterfaceControl
0x14002b4e4  mov     ebx, eax
0x14002b4e6  test    eax, eax
0x14002b4e8  js      short loc_14002B53D
0x14002b4ea  mov     rcx, [rbp+var_40]
0x14002b4ee  movzx   eax, word ptr [rbp+var_38+8]
0x14002b4f2  mov     [rcx+1Ch], eax
0x14002b4f5  movzx   eax, word ptr [rbp+var_38+0Ah]
0x14002b4f9  mov     [rcx+20h], eax
0x14002b4fc  mov     qword ptr [rcx+24h], 0
0x14002b504  movzx   edx, byte ptr [r12]
0x14002b509  mov     r9d, edx
0x14002b50c  mov     eax, edx
0x14002b50e  shr     eax, 1
0x14002b510  shr     r9d, 3
0x14002b514  and     eax, 1
0x14002b517  shl     eax, 3
0x14002b51a  and     r9d, 1
0x14002b51e  shl     r9d, 4
0x14002b522  or      r9d, eax
0x14002b525  mov     eax, edx
0x14002b527  shr     eax, 2
0x14002b52a  and     edx, 1
0x14002b52d  and     eax, 1
0x14002b530  shl     edx, 2
0x14002b533  or      r9d, eax
0x14002b536  or      r9d, edx
0x14002b539  mov     [rcx+2Ch], r9d
0x14002b53d  mov     rcx, [r15+1A8h]; Semaphore
0x14002b544  xor     r9d, r9d; Wait
0x14002b547  xor     edx, edx; Increment
0x14002b549  lea     r8d, [r9+1]; Adjustment
0x14002b54d  call    cs:__imp_KeReleaseSemaphore
0x14002b554  nop     dword ptr [rax+rax+00h]
0x14002b559  mov     rcx, rdi; Object
0x14002b55c  call    cs:__imp_KsReleaseControl
0x14002b563  nop     dword ptr [rax+rax+00h]
0x14002b568  mov     eax, ebx
0x14002b56a  mov     [r13+30h], ebx
0x14002b56e  mov     rcx, [rbp+var_8]
0x14002b572  xor     rcx, rsp; StackCookie
0x14002b575  call    __security_check_cookie
0x14002b57a  mov     rbx, [rsp+80h+arg_18]
0x14002b582  add     rsp, 80h
0x14002b589  pop     r15
0x14002b58b  pop     r14
0x14002b58d  pop     r13
0x14002b58f  pop     r12
0x14002b591  pop     rdi
0x14002b592  pop     rsi
0x14002b593  pop     rbp
0x14002b594  retn
```
