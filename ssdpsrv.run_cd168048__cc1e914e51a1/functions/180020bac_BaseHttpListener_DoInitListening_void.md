# BaseHttpListener::DoInitListening(void)

- ea: `0x180020bac`
- end: `0x180020f99`
- name: `?DoInitListening@BaseHttpListener@@IEAAJXZ`
- size: `1005`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001be0c`

## callees

- `0x180020bac`
- `0x1800234d8`
- `0x1800251e0`
- `0x180025ddc`
- `0x1800271fc`
- `0x1800287d0`
- `0x18002911c`
- `0x180029df0`
- `0x1800310d4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020e20`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180020e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020e4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ed0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020ed0`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::DoInitListening(BaseHttpListener *this)
{
  int HttpApi; // eax
  unsigned int v3; // ebx
  LPCSTR v4; // rcx
  int v5; // r14d
  int v6; // ebp
  __int64 v7; // rdx
  bool v8; // sf
  int v9; // eax
  int v10; // esi
  __int64 v11; // rax
  bool v12; // zf
  HANDLE Thread; // rax
  DWORD LastError; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned __int16 v18[256]; // [rsp+30h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  HttpApi = DelayLoadHttpApi::LoadHttpApi((BaseHttpListener *)((char *)this + 8));
  v3 = HttpApi;
  if ( HttpApi < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control )
      return v3;
    if ( (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
        (unsigned int)HttpApi);
      v4 = WPP_GLOBAL_Control;
    }
    goto LABEL_57;
  }
  v5 = 0;
  v3 = (*((__int64 (__fastcall **)(__int64, __int64, _QWORD))this + 3))(1, 1, 0);
  if ( v3 )
  {
    v6 = 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
      goto LABEL_13;
    v7 = 68;
LABEL_12:
    WPP_SF_d(*((_QWORD *)v4 + 2), v7, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v3);
    v4 = WPP_GLOBAL_Control;
LABEL_13:
    v8 = (v3 & 0x80000000) != 0;
    if ( (int)v3 <= 0 )
      goto LABEL_32;
    v3 = (unsigned __int16)v3;
    goto LABEL_30;
  }
  v6 = 1;
  v3 = (*((__int64 (__fastcall **)(char *, _QWORD))this + 4))((char *)this + 120, 0);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
      goto LABEL_13;
    v7 = 69;
    goto LABEL_12;
  }
  v5 = 1;
  memset_0(v18, 0, 0x1FEu);
  v3 = CalculateFullPrefixW(v18, 0xFFu, *((unsigned int *)this + 40), *((_QWORD *)this + 19));
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    goto LABEL_31;
  }
  v9 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD))this + 6))(*((_QWORD *)this + 15), v18, 0);
  v10 = v9;
  if ( !v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(*((_QWORD *)this + 19) + v11) );
    v12 = *((_DWORD *)this + 32) == 0;
    *((_DWORD *)this + 44) = v11;
    if ( !v12 )
      return v3;
    Thread = CreateThread(0, 0, BaseHttpListener::DoReceiveRequestHeadersStub, this, 0, 0);
    *((_QWORD *)this + 38) = Thread;
    if ( Thread )
    {
      BaseHttpListener::IncrThreadCount(this);
      *((_DWORD *)this + 32) = 1;
      return v3;
    }
    if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, LastError);
    }
    v15 = (*((__int64 (__fastcall **)(_QWORD, unsigned __int16 *))this + 8))(*((_QWORD *)this + 15), v18);
    if ( v15 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCSTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[28] & 1) == 0 )
        goto LABEL_47;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v15);
    }
    v4 = WPP_GLOBAL_Control;
LABEL_47:
    v3 = -2147467259;
LABEL_48:
    if ( *((_QWORD *)this + 15) )
    {
      CloseHandle(*((HANDLE *)this + 15));
      *((_QWORD *)this + 15) = 0;
      v4 = WPP_GLOBAL_Control;
    }
    goto LABEL_50;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      (unsigned int)WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      (unsigned int)v18,
      v9);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v10 > 0 )
  {
    v3 = (unsigned __int16)v10;
LABEL_30:
    v3 |= 0x80070000;
    goto LABEL_31;
  }
  v3 = v10;
LABEL_31:
  v8 = (v3 & 0x80000000) != 0;
LABEL_32:
  if ( !v8 )
    goto LABEL_56;
  if ( v5 )
    goto LABEL_48;
LABEL_50:
  if ( !v6 )
    goto LABEL_56;
  v16 = (*((__int64 (__fastcall **)(__int64, _QWORD))this + 7))(1, 0);
  if ( !v16 )
    goto LABEL_55;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[28] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v16);
LABEL_55:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_56:
  if ( !v3 )
    return v3;
LABEL_57:
  if ( v4 != (LPCSTR)&WPP_GLOBAL_Control && (v4[28] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 75, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180020bac  mov     [rsp+arg_8], rbx
0x180020bb1  mov     [rsp+arg_10], rbp
0x180020bb6  push    rsi
0x180020bb7  push    rdi
0x180020bb8  push    r12
0x180020bba  push    r13
0x180020bbc  push    r14
0x180020bbe  sub     rsp, 240h
0x180020bc5  mov     rax, cs:__security_cookie
0x180020bcc  xor     rax, rsp
0x180020bcf  mov     [rsp+268h+var_38], rax
0x180020bd7  mov     rdi, rcx
0x180020bda  mov     rcx, cs:WPP_GLOBAL_Control
0x180020be1  lea     r13, WPP_GLOBAL_Control
0x180020be8  cmp     rcx, r13
0x180020beb  jz      short loc_180020C0B
0x180020bed  test    dword ptr [rcx+1Ch], 100h
0x180020bf4  jz      short loc_180020C0B
0x180020bf6  mov     rcx, [rcx+10h]
0x180020bfa  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020c01  mov     edx, 42h ; 'B'
0x180020c06  call    WPP_SF_
0x180020c0b  lea     rcx, [rdi+8]; this
0x180020c0f  call    ?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::LoadHttpApi(void)
0x180020c14  mov     ebx, eax
0x180020c16  mov     r12d, 1
0x180020c1c  test    eax, eax
0x180020c1e  jns     short loc_180020C5E
0x180020c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c27  cmp     rcx, r13
0x180020c2a  jz      loc_180020F6A
0x180020c30  test    [rcx+1Ch], r12b
0x180020c34  jz      loc_180020F36
0x180020c3a  mov     rcx, [rcx+10h]
0x180020c3e  lea     edx, [r12+42h]
0x180020c43  mov     r9d, eax
0x180020c46  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020c4d  call    WPP_SF_d
0x180020c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c59  jmp     loc_180020F36
0x180020c5e  mov     ecx, cs:dword_18003DF48
0x180020c64  xor     r8d, r8d
0x180020c67  mov     rax, [rdi+18h]
0x180020c6b  mov     edx, r12d
0x180020c6e  xor     r14d, r14d
0x180020c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020c76  mov     ebx, eax
0x180020c78  test    eax, eax
0x180020c7a  jz      short loc_180020CBD
0x180020c7c  xor     ebp, ebp
0x180020c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020c85  cmp     rcx, r13
0x180020c88  jz      short loc_180020CAD
0x180020c8a  test    [rcx+1Ch], r12b
0x180020c8e  jz      short loc_180020CAD
0x180020c90  lea     edx, [rbp+44h]
0x180020c93  mov     rcx, [rcx+10h]
0x180020c97  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020c9e  mov     r9d, ebx
0x180020ca1  call    WPP_SF_d
0x180020ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cad  test    ebx, ebx
0x180020caf  jle     loc_180020DC6
0x180020cb5  movzx   ebx, bx
0x180020cb8  jmp     loc_180020DBE
0x180020cbd  mov     rax, [rdi+20h]
0x180020cc1  lea     rcx, [rdi+78h]
0x180020cc5  xor     edx, edx
0x180020cc7  mov     ebp, r12d
0x180020cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ccf  mov     ebx, eax
0x180020cd1  test    eax, eax
0x180020cd3  jz      short loc_180020CF1
0x180020cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cdc  cmp     rcx, r13
0x180020cdf  jz      short loc_180020CAD
0x180020ce1  test    dword ptr [rcx+1Ch], 100h
0x180020ce8  jz      short loc_180020CAD
0x180020cea  mov     edx, 45h ; 'E'
0x180020cef  jmp     short loc_180020C93
0x180020cf1  xor     edx, edx; Val
0x180020cf3  lea     rcx, [rsp+268h+var_238]; void *
0x180020cf8  mov     r8d, 1FEh; Size
0x180020cfe  mov     r14d, r12d
0x180020d01  call    memset_0
0x180020d06  mov     r9, [rdi+98h]
0x180020d0d  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x180020d12  mov     r8d, [rdi+0A0h]
0x180020d19  mov     edx, 0FFh; unsigned int
0x180020d1e  call    ?CalculateFullPrefixW@@YAJPEAGKZZ; CalculateFullPrefixW(ushort *,ulong,...)
0x180020d23  mov     ebx, eax
0x180020d25  test    eax, eax
0x180020d27  jz      short loc_180020D61
0x180020d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d30  cmp     rcx, r13
0x180020d33  jz      loc_180020DC4
0x180020d39  test    [rcx+1Ch], r12b
0x180020d3d  jz      loc_180020DC4
0x180020d43  mov     rcx, [rcx+10h]
0x180020d47  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020d4e  mov     edx, 46h ; 'F'
0x180020d53  call    WPP_SF_
0x180020d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d5f  jmp     short loc_180020DC4
0x180020d61  mov     rcx, [rdi+78h]
0x180020d65  lea     rdx, [rsp+268h+var_238]
0x180020d6a  mov     rax, [rdi+30h]
0x180020d6e  xor     r8d, r8d
0x180020d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d76  mov     esi, eax
0x180020d78  test    eax, eax
0x180020d7a  jz      short loc_180020DDA
0x180020d7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d83  cmp     rcx, r13
0x180020d86  jz      short loc_180020DB3
0x180020d88  test    [rcx+1Ch], r12b
0x180020d8c  jz      short loc_180020DB3
0x180020d8e  mov     rcx, [rcx+10h]
0x180020d92  lea     r9, [rsp+268h+var_238]
0x180020d97  mov     edx, 47h ; 'G'
0x180020d9c  mov     [rsp+268h+dwCreationFlags], eax
0x180020da0  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020da7  call    WPP_SF_Sd
0x180020dac  mov     rcx, cs:WPP_GLOBAL_Control
0x180020db3  test    esi, esi
0x180020db5  jg      short loc_180020DBB
0x180020db7  mov     ebx, esi
0x180020db9  jmp     short loc_180020DC4
0x180020dbb  movzx   ebx, si
0x180020dbe  or      ebx, 80070000h
0x180020dc4  test    ebx, ebx
0x180020dc6  jns     loc_180020F32
0x180020dcc  test    r14d, r14d
0x180020dcf  jnz     loc_180020EC5
0x180020dd5  jmp     loc_180020EEB
0x180020dda  mov     rcx, [rdi+98h]
0x180020de1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020de5  inc     rax
0x180020de8  cmp     byte ptr [rcx+rax], 0
0x180020dec  jnz     short loc_180020DE5
0x180020dee  cmp     dword ptr [rdi+80h], 0
0x180020df5  mov     [rdi+0B0h], eax
0x180020dfb  jnz     loc_180020F6A
0x180020e01  mov     [rsp+268h+lpThreadId], 0; lpThreadId
0x180020e0a  lea     r8, ?DoReceiveRequestHeadersStub@BaseHttpListener@@CAKPEAX@Z; lpStartAddress
0x180020e11  mov     r9, rdi; lpParameter
0x180020e14  mov     [rsp+268h+dwCreationFlags], 0; dwCreationFlags
0x180020e1c  xor     edx, edx; dwStackSize
0x180020e1e  xor     ecx, ecx; lpThreadAttributes
0x180020e20  call    cs:__imp_CreateThread
0x180020e27  nop     dword ptr [rax+rax+00h]
0x180020e2c  mov     [rdi+130h], rax
0x180020e33  test    rax, rax
0x180020e36  jnz     loc_180020F5B
0x180020e3c  mov     rax, cs:WPP_GLOBAL_Control
0x180020e43  cmp     rax, r13
0x180020e46  jz      short loc_180020E79
0x180020e48  test    [rax+1Ch], r12b
0x180020e4c  jz      short loc_180020E79
0x180020e4e  call    cs:__imp_GetLastError
0x180020e55  nop     dword ptr [rax+rax+00h]
0x180020e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e61  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020e68  mov     edx, 48h ; 'H'
0x180020e6d  mov     r9d, eax
0x180020e70  mov     rcx, [rcx+10h]
0x180020e74  call    WPP_SF_d
0x180020e79  mov     rcx, [rdi+78h]
0x180020e7d  lea     rdx, [rsp+268h+var_238]
0x180020e82  mov     rax, [rdi+40h]
0x180020e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e8b  test    eax, eax
0x180020e8d  jz      short loc_180020EB9
0x180020e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e96  cmp     rcx, r13
0x180020e99  jz      short loc_180020EC0
0x180020e9b  test    [rcx+1Ch], r12b
0x180020e9f  jz      short loc_180020EC0
0x180020ea1  mov     rcx, [rcx+10h]
0x180020ea5  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020eac  mov     edx, 49h ; 'I'
0x180020eb1  mov     r9d, eax
0x180020eb4  call    WPP_SF_d
0x180020eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ec0  mov     ebx, 80004005h
0x180020ec5  cmp     qword ptr [rdi+78h], 0
0x180020eca  jz      short loc_180020EEB
0x180020ecc  mov     rcx, [rdi+78h]; hObject
0x180020ed0  call    cs:__imp_CloseHandle
0x180020ed7  nop     dword ptr [rax+rax+00h]
0x180020edc  mov     qword ptr [rdi+78h], 0
0x180020ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x180020eeb  test    ebp, ebp
0x180020eed  jz      short loc_180020F32
0x180020eef  mov     rax, [rdi+38h]
0x180020ef3  xor     edx, edx
0x180020ef5  mov     ecx, r12d
0x180020ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020efd  test    eax, eax
0x180020eff  jz      short loc_180020F2B
0x180020f01  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f08  cmp     rcx, r13
0x180020f0b  jz      short loc_180020F32
0x180020f0d  test    [rcx+1Ch], r12b
0x180020f11  jz      short loc_180020F32
0x180020f13  mov     rcx, [rcx+10h]
0x180020f17  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020f1e  mov     edx, 4Ah ; 'J'
0x180020f23  mov     r9d, eax
0x180020f26  call    WPP_SF_d
0x180020f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f32  test    ebx, ebx
0x180020f34  jz      short loc_180020F6A
0x180020f36  cmp     rcx, r13
0x180020f39  jz      short loc_180020F6A
0x180020f3b  test    [rcx+1Ch], r12b
0x180020f3f  jz      short loc_180020F6A
0x180020f41  mov     rcx, [rcx+10h]
0x180020f45  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180020f4c  mov     edx, 4Bh ; 'K'
0x180020f51  mov     r9d, ebx
0x180020f54  call    WPP_SF_d
0x180020f59  jmp     short loc_180020F6A
0x180020f5b  mov     rcx, rdi; this
0x180020f5e  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x180020f63  mov     [rdi+80h], r12d
0x180020f6a  mov     eax, ebx
0x180020f6c  mov     rcx, [rsp+268h+var_38]
0x180020f74  xor     rcx, rsp; StackCookie
0x180020f77  call    __security_check_cookie
0x180020f7c  lea     r11, [rsp+268h+var_28]
0x180020f84  mov     rbx, [r11+38h]
0x180020f88  mov     rbp, [r11+40h]
0x180020f8c  mov     rsp, r11
0x180020f8f  pop     r14
0x180020f91  pop     r13
0x180020f93  pop     r12
0x180020f95  pop     rdi
0x180020f96  pop     rsi
0x180020f97  retn
```
