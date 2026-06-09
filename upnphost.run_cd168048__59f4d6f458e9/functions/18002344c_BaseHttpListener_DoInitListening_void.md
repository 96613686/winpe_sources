# BaseHttpListener::DoInitListening(void)

- ea: `0x18002344c`
- end: `0x180023839`
- name: `?DoInitListening@BaseHttpListener@@IEAAJXZ`
- size: `1005`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800226ac`

## callees

- `0x18002344c`
- `0x180023840`
- `0x180023f74`
- `0x180029a38`
- `0x18003b1cc`
- `0x18003c018`
- `0x18003cb60`
- `0x18003d4b0`
- `0x180049258`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800236ee`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800236c0`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800236c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023770`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180023770`

## pseudocode

```c
__int64 __fastcall BaseHttpListener::DoInitListening(BaseHttpListener *this)
{
  int HttpApi; // eax
  unsigned int v3; // ebx
  STRSAFE_PCNZWCH v4; // rcx
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
  wchar_t pszDest[256]; // [rsp+30h] [rbp-238h] BYREF

  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
  HttpApi = DelayLoadHttpApi::LoadHttpApi((BaseHttpListener *)((char *)this + 8));
  v3 = HttpApi;
  if ( HttpApi < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control )
      return v3;
    if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
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
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
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
    if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0 )
    {
      goto LABEL_13;
    }
    v7 = 69;
    goto LABEL_12;
  }
  v5 = 1;
  memset_0(pszDest, 0, 0x1FEu);
  v3 = CalculateFullPrefixW(pszDest, 0xFFu, *((unsigned int *)this + 40), *((_QWORD *)this + 19));
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
    goto LABEL_31;
  }
  v9 = (*((__int64 (__fastcall **)(_QWORD, wchar_t *, _QWORD))this + 6))(*((_QWORD *)this + 15), pszDest, 0);
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
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, LastError);
    }
    v15 = (*((__int64 (__fastcall **)(_QWORD, wchar_t *))this + 8))(*((_QWORD *)this + 15), pszDest);
    if ( v15 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
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
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      71,
      (unsigned int)WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids,
      (unsigned int)pszDest,
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
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v16);
LABEL_55:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_56:
  if ( !v3 )
    return v3;
LABEL_57:
  if ( v4 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v4[14] & 1) != 0 )
    WPP_SF_d(*((_QWORD *)v4 + 2), 75, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x18002344c  mov     [rsp+arg_8], rbx
0x180023451  mov     [rsp+arg_10], rbp
0x180023456  push    rsi
0x180023457  push    rdi
0x180023458  push    r12
0x18002345a  push    r13
0x18002345c  push    r14
0x18002345e  sub     rsp, 240h
0x180023465  mov     rax, cs:__security_cookie
0x18002346c  xor     rax, rsp
0x18002346f  mov     [rsp+268h+var_38], rax
0x180023477  mov     rdi, rcx
0x18002347a  mov     rcx, cs:WPP_GLOBAL_Control
0x180023481  lea     r13, WPP_GLOBAL_Control
0x180023488  cmp     rcx, r13
0x18002348b  jz      short loc_1800234AB
0x18002348d  test    dword ptr [rcx+1Ch], 100h
0x180023494  jz      short loc_1800234AB
0x180023496  mov     rcx, [rcx+10h]
0x18002349a  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800234a1  mov     edx, 42h ; 'B'
0x1800234a6  call    WPP_SF_
0x1800234ab  lea     rcx, [rdi+8]; this
0x1800234af  call    ?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::LoadHttpApi(void)
0x1800234b4  mov     ebx, eax
0x1800234b6  mov     r12d, 1
0x1800234bc  test    eax, eax
0x1800234be  jns     short loc_1800234FE
0x1800234c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234c7  cmp     rcx, r13
0x1800234ca  jz      loc_18002380A
0x1800234d0  test    [rcx+1Ch], r12b
0x1800234d4  jz      loc_1800237D6
0x1800234da  mov     rcx, [rcx+10h]
0x1800234de  lea     edx, [r12+42h]
0x1800234e3  mov     r9d, eax
0x1800234e6  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800234ed  call    WPP_SF_d
0x1800234f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234f9  jmp     loc_1800237D6
0x1800234fe  mov     ecx, cs:dword_18006C1A8
0x180023504  xor     r8d, r8d
0x180023507  mov     rax, [rdi+18h]
0x18002350b  mov     edx, r12d
0x18002350e  xor     r14d, r14d
0x180023511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023516  mov     ebx, eax
0x180023518  test    eax, eax
0x18002351a  jz      short loc_18002355D
0x18002351c  xor     ebp, ebp
0x18002351e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023525  cmp     rcx, r13
0x180023528  jz      short loc_18002354D
0x18002352a  test    [rcx+1Ch], r12b
0x18002352e  jz      short loc_18002354D
0x180023530  lea     edx, [rbp+44h]
0x180023533  mov     rcx, [rcx+10h]
0x180023537  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002353e  mov     r9d, ebx
0x180023541  call    WPP_SF_d
0x180023546  mov     rcx, cs:WPP_GLOBAL_Control
0x18002354d  test    ebx, ebx
0x18002354f  jle     loc_180023666
0x180023555  movzx   ebx, bx
0x180023558  jmp     loc_18002365E
0x18002355d  mov     rax, [rdi+20h]
0x180023561  lea     rcx, [rdi+78h]
0x180023565  xor     edx, edx
0x180023567  mov     ebp, r12d
0x18002356a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002356f  mov     ebx, eax
0x180023571  test    eax, eax
0x180023573  jz      short loc_180023591
0x180023575  mov     rcx, cs:WPP_GLOBAL_Control
0x18002357c  cmp     rcx, r13
0x18002357f  jz      short loc_18002354D
0x180023581  test    dword ptr [rcx+1Ch], 100h
0x180023588  jz      short loc_18002354D
0x18002358a  mov     edx, 45h ; 'E'
0x18002358f  jmp     short loc_180023533
0x180023591  xor     edx, edx; Val
0x180023593  lea     rcx, [rsp+268h+pszDest]; void *
0x180023598  mov     r8d, 1FEh; Size
0x18002359e  mov     r14d, r12d
0x1800235a1  call    memset_0
0x1800235a6  mov     r9, [rdi+98h]
0x1800235ad  lea     rcx, [rsp+268h+pszDest]; pszDest
0x1800235b2  mov     r8d, [rdi+0A0h]
0x1800235b9  mov     edx, 0FFh; cchDest
0x1800235be  call    ?CalculateFullPrefixW@@YAJPEAGKZZ; CalculateFullPrefixW(ushort *,ulong,...)
0x1800235c3  mov     ebx, eax
0x1800235c5  test    eax, eax
0x1800235c7  jz      short loc_180023601
0x1800235c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235d0  cmp     rcx, r13
0x1800235d3  jz      loc_180023664
0x1800235d9  test    [rcx+1Ch], r12b
0x1800235dd  jz      loc_180023664
0x1800235e3  mov     rcx, [rcx+10h]
0x1800235e7  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800235ee  mov     edx, 46h ; 'F'
0x1800235f3  call    WPP_SF_
0x1800235f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800235ff  jmp     short loc_180023664
0x180023601  mov     rcx, [rdi+78h]
0x180023605  lea     rdx, [rsp+268h+pszDest]
0x18002360a  mov     rax, [rdi+30h]
0x18002360e  xor     r8d, r8d
0x180023611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023616  mov     esi, eax
0x180023618  test    eax, eax
0x18002361a  jz      short loc_18002367A
0x18002361c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023623  cmp     rcx, r13
0x180023626  jz      short loc_180023653
0x180023628  test    [rcx+1Ch], r12b
0x18002362c  jz      short loc_180023653
0x18002362e  mov     rcx, [rcx+10h]
0x180023632  lea     r9, [rsp+268h+pszDest]
0x180023637  mov     edx, 47h ; 'G'
0x18002363c  mov     [rsp+268h+dwCreationFlags], eax
0x180023640  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023647  call    WPP_SF_Sd
0x18002364c  mov     rcx, cs:WPP_GLOBAL_Control
0x180023653  test    esi, esi
0x180023655  jg      short loc_18002365B
0x180023657  mov     ebx, esi
0x180023659  jmp     short loc_180023664
0x18002365b  movzx   ebx, si
0x18002365e  or      ebx, 80070000h
0x180023664  test    ebx, ebx
0x180023666  jns     loc_1800237D2
0x18002366c  test    r14d, r14d
0x18002366f  jnz     loc_180023765
0x180023675  jmp     loc_18002378B
0x18002367a  mov     rcx, [rdi+98h]
0x180023681  or      rax, 0FFFFFFFFFFFFFFFFh
0x180023685  inc     rax
0x180023688  cmp     byte ptr [rcx+rax], 0
0x18002368c  jnz     short loc_180023685
0x18002368e  cmp     dword ptr [rdi+80h], 0
0x180023695  mov     [rdi+0B0h], eax
0x18002369b  jnz     loc_18002380A
0x1800236a1  mov     [rsp+268h+lpThreadId], 0; lpThreadId
0x1800236aa  lea     r8, ?DoReceiveRequestHeadersStub@BaseHttpListener@@CAKPEAX@Z; lpStartAddress
0x1800236b1  mov     r9, rdi; lpParameter
0x1800236b4  mov     [rsp+268h+dwCreationFlags], 0; dwCreationFlags
0x1800236bc  xor     edx, edx; dwStackSize
0x1800236be  xor     ecx, ecx; lpThreadAttributes
0x1800236c0  call    cs:__imp_CreateThread
0x1800236c7  nop     dword ptr [rax+rax+00h]
0x1800236cc  mov     [rdi+130h], rax
0x1800236d3  test    rax, rax
0x1800236d6  jnz     loc_1800237FB
0x1800236dc  mov     rax, cs:WPP_GLOBAL_Control
0x1800236e3  cmp     rax, r13
0x1800236e6  jz      short loc_180023719
0x1800236e8  test    [rax+1Ch], r12b
0x1800236ec  jz      short loc_180023719
0x1800236ee  call    cs:__imp_GetLastError
0x1800236f5  nop     dword ptr [rax+rax+00h]
0x1800236fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180023701  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180023708  mov     edx, 48h ; 'H'
0x18002370d  mov     r9d, eax
0x180023710  mov     rcx, [rcx+10h]
0x180023714  call    WPP_SF_d
0x180023719  mov     rcx, [rdi+78h]
0x18002371d  lea     rdx, [rsp+268h+pszDest]
0x180023722  mov     rax, [rdi+40h]
0x180023726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002372b  test    eax, eax
0x18002372d  jz      short loc_180023759
0x18002372f  mov     rcx, cs:WPP_GLOBAL_Control
0x180023736  cmp     rcx, r13
0x180023739  jz      short loc_180023760
0x18002373b  test    [rcx+1Ch], r12b
0x18002373f  jz      short loc_180023760
0x180023741  mov     rcx, [rcx+10h]
0x180023745  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002374c  mov     edx, 49h ; 'I'
0x180023751  mov     r9d, eax
0x180023754  call    WPP_SF_d
0x180023759  mov     rcx, cs:WPP_GLOBAL_Control
0x180023760  mov     ebx, 80004005h
0x180023765  cmp     qword ptr [rdi+78h], 0
0x18002376a  jz      short loc_18002378B
0x18002376c  mov     rcx, [rdi+78h]; hObject
0x180023770  call    cs:__imp_CloseHandle
0x180023777  nop     dword ptr [rax+rax+00h]
0x18002377c  mov     qword ptr [rdi+78h], 0
0x180023784  mov     rcx, cs:WPP_GLOBAL_Control
0x18002378b  test    ebp, ebp
0x18002378d  jz      short loc_1800237D2
0x18002378f  mov     rax, [rdi+38h]
0x180023793  xor     edx, edx
0x180023795  mov     ecx, r12d
0x180023798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002379d  test    eax, eax
0x18002379f  jz      short loc_1800237CB
0x1800237a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237a8  cmp     rcx, r13
0x1800237ab  jz      short loc_1800237D2
0x1800237ad  test    [rcx+1Ch], r12b
0x1800237b1  jz      short loc_1800237D2
0x1800237b3  mov     rcx, [rcx+10h]
0x1800237b7  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800237be  mov     edx, 4Ah ; 'J'
0x1800237c3  mov     r9d, eax
0x1800237c6  call    WPP_SF_d
0x1800237cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800237d2  test    ebx, ebx
0x1800237d4  jz      short loc_18002380A
0x1800237d6  cmp     rcx, r13
0x1800237d9  jz      short loc_18002380A
0x1800237db  test    [rcx+1Ch], r12b
0x1800237df  jz      short loc_18002380A
0x1800237e1  mov     rcx, [rcx+10h]
0x1800237e5  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800237ec  mov     edx, 4Bh ; 'K'
0x1800237f1  mov     r9d, ebx
0x1800237f4  call    WPP_SF_d
0x1800237f9  jmp     short loc_18002380A
0x1800237fb  mov     rcx, rdi; this
0x1800237fe  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x180023803  mov     [rdi+80h], r12d
0x18002380a  mov     eax, ebx
0x18002380c  mov     rcx, [rsp+268h+var_38]
0x180023814  xor     rcx, rsp; StackCookie
0x180023817  call    __security_check_cookie
0x18002381c  lea     r11, [rsp+268h+var_28]
0x180023824  mov     rbx, [r11+38h]
0x180023828  mov     rbp, [r11+40h]
0x18002382c  mov     rsp, r11
0x18002382f  pop     r14
0x180023831  pop     r13
0x180023833  pop     r12
0x180023835  pop     rdi
0x180023836  pop     rsi
0x180023837  retn
```
