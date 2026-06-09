# BaseHttpListener::DoInitListening(void)

- ea: `0x18001f3e0`
- end: `0x18001f7ba`
- name: `?DoInitListening@BaseHttpListener@@IEAAJXZ`
- size: `986`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001aaac`

## callees

- `0x18001f3e0`
- `0x180021c04`
- `0x1800237d8`
- `0x180024328`
- `0x1800255a8`
- `0x180026a30`
- `0x18002735c`
- `0x180028000`
- `0x18002ee9c`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f654`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f67c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f67c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f6f8`

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
0x18001f3e0  mov     [rsp+arg_8], rbx
0x18001f3e5  mov     [rsp+arg_10], rbp
0x18001f3ea  push    rsi
0x18001f3eb  push    rdi
0x18001f3ec  push    r12
0x18001f3ee  push    r13
0x18001f3f0  push    r14
0x18001f3f2  sub     rsp, 240h
0x18001f3f9  mov     rax, cs:__security_cookie
0x18001f400  xor     rax, rsp
0x18001f403  mov     [rsp+268h+var_38], rax
0x18001f40b  mov     rdi, rcx
0x18001f40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f415  lea     r13, WPP_GLOBAL_Control
0x18001f41c  cmp     rcx, r13
0x18001f41f  jz      short loc_18001F43F
0x18001f421  test    dword ptr [rcx+1Ch], 100h
0x18001f428  jz      short loc_18001F43F
0x18001f42a  mov     rcx, [rcx+10h]
0x18001f42e  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f435  mov     edx, 42h ; 'B'
0x18001f43a  call    WPP_SF_
0x18001f43f  lea     rcx, [rdi+8]; this
0x18001f443  call    ?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::LoadHttpApi(void)
0x18001f448  mov     ebx, eax
0x18001f44a  mov     r12d, 1
0x18001f450  test    eax, eax
0x18001f452  jns     short loc_18001F492
0x18001f454  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f45b  cmp     rcx, r13
0x18001f45e  jz      loc_18001F78C
0x18001f464  test    [rcx+1Ch], r12b
0x18001f468  jz      loc_18001F758
0x18001f46e  mov     rcx, [rcx+10h]
0x18001f472  lea     edx, [r12+42h]
0x18001f477  mov     r9d, eax
0x18001f47a  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f481  call    WPP_SF_d
0x18001f486  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f48d  jmp     loc_18001F758
0x18001f492  mov     ecx, cs:dword_18003AF38
0x18001f498  xor     r8d, r8d
0x18001f49b  mov     rax, [rdi+18h]
0x18001f49f  mov     edx, r12d
0x18001f4a2  xor     r14d, r14d
0x18001f4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4aa  mov     ebx, eax
0x18001f4ac  test    eax, eax
0x18001f4ae  jz      short loc_18001F4F1
0x18001f4b0  xor     ebp, ebp
0x18001f4b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4b9  cmp     rcx, r13
0x18001f4bc  jz      short loc_18001F4E1
0x18001f4be  test    [rcx+1Ch], r12b
0x18001f4c2  jz      short loc_18001F4E1
0x18001f4c4  lea     edx, [rbp+44h]
0x18001f4c7  mov     rcx, [rcx+10h]
0x18001f4cb  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f4d2  mov     r9d, ebx
0x18001f4d5  call    WPP_SF_d
0x18001f4da  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f4e1  test    ebx, ebx
0x18001f4e3  jle     loc_18001F5FA
0x18001f4e9  movzx   ebx, bx
0x18001f4ec  jmp     loc_18001F5F2
0x18001f4f1  mov     rax, [rdi+20h]
0x18001f4f5  lea     rcx, [rdi+78h]
0x18001f4f9  xor     edx, edx
0x18001f4fb  mov     ebp, r12d
0x18001f4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f503  mov     ebx, eax
0x18001f505  test    eax, eax
0x18001f507  jz      short loc_18001F525
0x18001f509  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f510  cmp     rcx, r13
0x18001f513  jz      short loc_18001F4E1
0x18001f515  test    dword ptr [rcx+1Ch], 100h
0x18001f51c  jz      short loc_18001F4E1
0x18001f51e  mov     edx, 45h ; 'E'
0x18001f523  jmp     short loc_18001F4C7
0x18001f525  xor     edx, edx; Val
0x18001f527  lea     rcx, [rsp+268h+var_238]; void *
0x18001f52c  mov     r8d, 1FEh; Size
0x18001f532  mov     r14d, r12d
0x18001f535  call    memset_0
0x18001f53a  mov     r9, [rdi+98h]
0x18001f541  lea     rcx, [rsp+268h+var_238]; unsigned __int16 *
0x18001f546  mov     r8d, [rdi+0A0h]
0x18001f54d  mov     edx, 0FFh; unsigned int
0x18001f552  call    ?CalculateFullPrefixW@@YAJPEAGKZZ; CalculateFullPrefixW(ushort *,ulong,...)
0x18001f557  mov     ebx, eax
0x18001f559  test    eax, eax
0x18001f55b  jz      short loc_18001F595
0x18001f55d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f564  cmp     rcx, r13
0x18001f567  jz      loc_18001F5F8
0x18001f56d  test    [rcx+1Ch], r12b
0x18001f571  jz      loc_18001F5F8
0x18001f577  mov     rcx, [rcx+10h]
0x18001f57b  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f582  mov     edx, 46h ; 'F'
0x18001f587  call    WPP_SF_
0x18001f58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f593  jmp     short loc_18001F5F8
0x18001f595  mov     rcx, [rdi+78h]
0x18001f599  lea     rdx, [rsp+268h+var_238]
0x18001f59e  mov     rax, [rdi+30h]
0x18001f5a2  xor     r8d, r8d
0x18001f5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5aa  mov     esi, eax
0x18001f5ac  test    eax, eax
0x18001f5ae  jz      short loc_18001F60E
0x18001f5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5b7  cmp     rcx, r13
0x18001f5ba  jz      short loc_18001F5E7
0x18001f5bc  test    [rcx+1Ch], r12b
0x18001f5c0  jz      short loc_18001F5E7
0x18001f5c2  mov     rcx, [rcx+10h]
0x18001f5c6  lea     r9, [rsp+268h+var_238]
0x18001f5cb  mov     edx, 47h ; 'G'
0x18001f5d0  mov     [rsp+268h+dwCreationFlags], eax
0x18001f5d4  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f5db  call    WPP_SF_Sd
0x18001f5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f5e7  test    esi, esi
0x18001f5e9  jg      short loc_18001F5EF
0x18001f5eb  mov     ebx, esi
0x18001f5ed  jmp     short loc_18001F5F8
0x18001f5ef  movzx   ebx, si
0x18001f5f2  or      ebx, 80070000h
0x18001f5f8  test    ebx, ebx
0x18001f5fa  jns     loc_18001F754
0x18001f600  test    r14d, r14d
0x18001f603  jnz     loc_18001F6ED
0x18001f609  jmp     loc_18001F70D
0x18001f60e  mov     rcx, [rdi+98h]
0x18001f615  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f619  inc     rax
0x18001f61c  cmp     byte ptr [rcx+rax], 0
0x18001f620  jnz     short loc_18001F619
0x18001f622  cmp     dword ptr [rdi+80h], 0
0x18001f629  mov     [rdi+0B0h], eax
0x18001f62f  jnz     loc_18001F78C
0x18001f635  mov     [rsp+268h+lpThreadId], 0; lpThreadId
0x18001f63e  lea     r8, ?DoReceiveRequestHeadersStub@BaseHttpListener@@CAKPEAX@Z; lpStartAddress
0x18001f645  mov     r9, rdi; lpParameter
0x18001f648  mov     [rsp+268h+dwCreationFlags], 0; dwCreationFlags
0x18001f650  xor     edx, edx; dwStackSize
0x18001f652  xor     ecx, ecx; lpThreadAttributes
0x18001f654  call    cs:__imp_CreateThread
0x18001f65a  mov     [rdi+130h], rax
0x18001f661  test    rax, rax
0x18001f664  jnz     loc_18001F77D
0x18001f66a  mov     rax, cs:WPP_GLOBAL_Control
0x18001f671  cmp     rax, r13
0x18001f674  jz      short loc_18001F6A1
0x18001f676  test    [rax+1Ch], r12b
0x18001f67a  jz      short loc_18001F6A1
0x18001f67c  call    cs:__imp_GetLastError
0x18001f682  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f689  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f690  mov     edx, 48h ; 'H'
0x18001f695  mov     r9d, eax
0x18001f698  mov     rcx, [rcx+10h]
0x18001f69c  call    WPP_SF_d
0x18001f6a1  mov     rcx, [rdi+78h]
0x18001f6a5  lea     rdx, [rsp+268h+var_238]
0x18001f6aa  mov     rax, [rdi+40h]
0x18001f6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6b3  test    eax, eax
0x18001f6b5  jz      short loc_18001F6E1
0x18001f6b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6be  cmp     rcx, r13
0x18001f6c1  jz      short loc_18001F6E8
0x18001f6c3  test    [rcx+1Ch], r12b
0x18001f6c7  jz      short loc_18001F6E8
0x18001f6c9  mov     rcx, [rcx+10h]
0x18001f6cd  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f6d4  mov     edx, 49h ; 'I'
0x18001f6d9  mov     r9d, eax
0x18001f6dc  call    WPP_SF_d
0x18001f6e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6e8  mov     ebx, 80004005h
0x18001f6ed  cmp     qword ptr [rdi+78h], 0
0x18001f6f2  jz      short loc_18001F70D
0x18001f6f4  mov     rcx, [rdi+78h]; hObject
0x18001f6f8  call    cs:__imp_CloseHandle
0x18001f6fe  mov     qword ptr [rdi+78h], 0
0x18001f706  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f70d  test    ebp, ebp
0x18001f70f  jz      short loc_18001F754
0x18001f711  mov     rax, [rdi+38h]
0x18001f715  xor     edx, edx
0x18001f717  mov     ecx, r12d
0x18001f71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f71f  test    eax, eax
0x18001f721  jz      short loc_18001F74D
0x18001f723  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f72a  cmp     rcx, r13
0x18001f72d  jz      short loc_18001F754
0x18001f72f  test    [rcx+1Ch], r12b
0x18001f733  jz      short loc_18001F754
0x18001f735  mov     rcx, [rcx+10h]
0x18001f739  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f740  mov     edx, 4Ah ; 'J'
0x18001f745  mov     r9d, eax
0x18001f748  call    WPP_SF_d
0x18001f74d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f754  test    ebx, ebx
0x18001f756  jz      short loc_18001F78C
0x18001f758  cmp     rcx, r13
0x18001f75b  jz      short loc_18001F78C
0x18001f75d  test    [rcx+1Ch], r12b
0x18001f761  jz      short loc_18001F78C
0x18001f763  mov     rcx, [rcx+10h]
0x18001f767  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18001f76e  mov     edx, 4Bh ; 'K'
0x18001f773  mov     r9d, ebx
0x18001f776  call    WPP_SF_d
0x18001f77b  jmp     short loc_18001F78C
0x18001f77d  mov     rcx, rdi; this
0x18001f780  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x18001f785  mov     [rdi+80h], r12d
0x18001f78c  mov     eax, ebx
0x18001f78e  mov     rcx, [rsp+268h+var_38]
0x18001f796  xor     rcx, rsp; StackCookie
0x18001f799  call    __security_check_cookie
0x18001f79e  lea     r11, [rsp+268h+var_28]
0x18001f7a6  mov     rbx, [r11+38h]
0x18001f7aa  mov     rbp, [r11+40h]
0x18001f7ae  mov     rsp, r11
0x18001f7b1  pop     r14
0x18001f7b3  pop     r13
0x18001f7b5  pop     r12
0x18001f7b7  pop     rdi
0x18001f7b8  pop     rsi
0x18001f7b9  retn
```
