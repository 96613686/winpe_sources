# ChangeAccountPasswordCommon(void *,void *,void *,void *,void *,uchar,ulong,_SecBufferDesc *,uchar)

- ea: `0x18001a33c`
- end: `0x18001a4fb`
- name: `?ChangeAccountPasswordCommon@@YAJPEAX0000EKPEAU_SecBufferDesc@@E@Z`
- size: `447`
- prototype: `int(void *, void *, void *, void *, void *, unsigned __int8, unsigned int, struct _SecBufferDesc *, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a7b0`
- `0x18001a800`

## callees

- `0x180007b58`
- `0x180009c90`
- `0x18001a33c`
- `0x18001b048`
- `0x18001b298`
- `0x18001b40c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a3f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a464`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a3f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001a464`

## pseudocode

```c
__int64 __fastcall ChangeAccountPasswordCommon(
        const char *a1,
        __int64 a2,
        __int64 a3,
        void *a4,
        void *a5,
        unsigned __int8 a6,
        unsigned int a7,
        struct _SecBufferDesc *a8,
        unsigned __int8 a9)
{
  __int64 result; // rax
  _QWORD *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rax
  _QWORD *v17; // rdi
  __int64 v18; // rax
  unsigned int v19; // ebx
  int v20; // [rsp+28h] [rbp-60h]
  LPVOID lpTlsValue; // [rsp+90h] [rbp+8h] BYREF

  lpTlsValue = 0;
  if ( !a1 )
    return 2148074245LL;
  if ( !a9 )
  {
    result = SecLocatePackageExA(0, a1, (struct _DLL_SECURITY_PACKAGE **)&lpTlsValue);
    if ( (int)result < 0 )
      return result;
    v17 = lpTlsValue;
    v18 = *((_QWORD *)lpTlsValue + 20);
    if ( *(_DWORD *)v18 >= 4u && *(_QWORD *)(v18 + 232) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_Sss(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3);
      TlsSetValue(SecTlsPackage, v17);
      v16 = v17[20];
      goto LABEL_18;
    }
LABEL_19:
    v19 = -2146893054;
    goto LABEL_20;
  }
  result = SecLocatePackageExW(0, a1, &lpTlsValue);
  if ( (int)result < 0 )
    return result;
  v14 = lpTlsValue;
  v15 = *((_QWORD *)lpTlsValue + 21);
  if ( *(_DWORD *)v15 < 4u || !*(_QWORD *)(v15 + 232) )
    goto LABEL_19;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3);
  TlsSetValue(SecTlsPackage, v14);
  v16 = v14[21];
LABEL_18:
  LOBYTE(v20) = a6;
  v19 = (*(__int64 (__fastcall **)(const char *, __int64, __int64, void *, void *, int, unsigned int, struct _SecBufferDesc *))(v16 + 232))(
          a1,
          a2,
          a3,
          a4,
          a5,
          v20,
          a7,
          a8);
LABEL_20:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids, v19);
  return v19;
}

```

## disassembly

```asm
0x18001a33c  mov     rax, rsp
0x18001a33f  push    rbx
0x18001a340  push    rbp
0x18001a341  push    rsi
0x18001a342  push    rdi
0x18001a343  push    r12
0x18001a345  push    r14
0x18001a347  sub     rsp, 58h
0x18001a34b  mov     qword ptr [rax+8], 0
0x18001a353  mov     r14, r9
0x18001a356  mov     rsi, r8
0x18001a359  mov     rbp, rdx
0x18001a35c  mov     rbx, rcx
0x18001a35f  test    rcx, rcx
0x18001a362  jnz     short loc_18001A36E
0x18001a364  mov     eax, 80090305h
0x18001a369  jmp     loc_18001A4EE
0x18001a36e  xor     ecx, ecx; int
0x18001a370  lea     r12, WPP_GLOBAL_Control
0x18001a377  lea     r8, [rsp+88h+lpTlsValue]
0x18001a37f  mov     rdx, rbx
0x18001a382  cmp     [rsp+88h+arg_40], cl
0x18001a389  jz      short loc_18001A3FF
0x18001a38b  call    SecLocatePackageExW
0x18001a390  test    eax, eax
0x18001a392  js      loc_18001A4EE
0x18001a398  mov     rdi, [rsp+88h+lpTlsValue]
0x18001a3a0  mov     rax, [rdi+0A8h]
0x18001a3a7  cmp     dword ptr [rax], 4
0x18001a3aa  jb      loc_18001A4BD
0x18001a3b0  cmp     qword ptr [rax+0E8h], 0
0x18001a3b8  jz      loc_18001A4BD
0x18001a3be  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3c5  cmp     rcx, r12
0x18001a3c8  jz      short loc_18001A3E7
0x18001a3ca  test    byte ptr [rcx+1Ch], 4
0x18001a3ce  jz      short loc_18001A3E7
0x18001a3d0  mov     r9, [rdi+68h]
0x18001a3d4  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a3d8  mov     [rsp+88h+var_60], rsi; __int64
0x18001a3dd  mov     [rsp+88h+var_68], rbp; __int64
0x18001a3e2  call    WPP_SF_SSS
0x18001a3e7  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001a3ed  mov     rdx, rdi; lpTlsValue
0x18001a3f0  call    cs:__imp_TlsSetValue
0x18001a3f6  mov     rax, [rdi+0A8h]
0x18001a3fd  jmp     short loc_18001A471
0x18001a3ff  call    SecLocatePackageExA
0x18001a404  test    eax, eax
0x18001a406  js      loc_18001A4EE
0x18001a40c  mov     rdi, [rsp+88h+lpTlsValue]
0x18001a414  mov     rax, [rdi+0A0h]
0x18001a41b  cmp     dword ptr [rax], 4
0x18001a41e  jb      loc_18001A4BD
0x18001a424  cmp     qword ptr [rax+0E8h], 0
0x18001a42c  jz      loc_18001A4BD
0x18001a432  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a439  cmp     rcx, r12
0x18001a43c  jz      short loc_18001A45B
0x18001a43e  test    byte ptr [rcx+1Ch], 4
0x18001a442  jz      short loc_18001A45B
0x18001a444  mov     r9, [rdi+68h]
0x18001a448  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a44c  mov     [rsp+88h+var_60], rsi; __int64
0x18001a451  mov     [rsp+88h+var_68], rbp; __int64
0x18001a456  call    WPP_SF_Sss
0x18001a45b  mov     ecx, cs:SecTlsPackage; dwTlsIndex
0x18001a461  mov     rdx, rdi; lpTlsValue
0x18001a464  call    cs:__imp_TlsSetValue
0x18001a46a  mov     rax, [rdi+0A0h]
0x18001a471  mov     rcx, [rsp+88h+arg_38]
0x18001a479  mov     r9, r14
0x18001a47c  mov     rax, [rax+0E8h]
0x18001a483  mov     r8, rsi
0x18001a486  mov     [rsp+88h+var_50], rcx
0x18001a48b  mov     rdx, rbp
0x18001a48e  mov     ecx, [rsp+88h+arg_30]
0x18001a495  mov     [rsp+88h+var_58], ecx
0x18001a499  mov     cl, [rsp+88h+arg_28]
0x18001a4a0  mov     byte ptr [rsp+88h+var_60], cl
0x18001a4a4  mov     rcx, [rsp+88h+arg_20]
0x18001a4ac  mov     [rsp+88h+var_68], rcx
0x18001a4b1  mov     rcx, rbx
0x18001a4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4b9  mov     ebx, eax
0x18001a4bb  jmp     short loc_18001A4C2
0x18001a4bd  mov     ebx, 80090302h
0x18001a4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a4c9  cmp     rcx, r12
0x18001a4cc  jz      short loc_18001A4EC
0x18001a4ce  test    byte ptr [rcx+1Ch], 4
0x18001a4d2  jz      short loc_18001A4EC
0x18001a4d4  mov     rcx, [rcx+10h]
0x18001a4d8  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x18001a4df  mov     edx, 0Ch
0x18001a4e4  mov     r9d, ebx
0x18001a4e7  call    WPP_SF_D
0x18001a4ec  mov     eax, ebx
0x18001a4ee  add     rsp, 58h
0x18001a4f2  pop     r14
0x18001a4f4  pop     r12
0x18001a4f6  pop     rdi
0x18001a4f7  pop     rsi
0x18001a4f8  pop     rbp
0x18001a4f9  pop     rbx
0x18001a4fa  retn
```
