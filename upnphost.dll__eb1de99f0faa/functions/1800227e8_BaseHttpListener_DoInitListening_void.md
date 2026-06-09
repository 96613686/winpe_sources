# BaseHttpListener::DoInitListening(void)

- ea: `0x1800227e8`
- end: `0x180022bc2`
- name: `?DoInitListening@BaseHttpListener@@IEAAJXZ`
- size: `986`
- prototype: `__int64 __fastcall(BaseHttpListener *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180021ab4`

## callees

- `0x1800227e8`
- `0x180022bc8`
- `0x180023288`
- `0x1800287a4`
- `0x180038ce4`
- `0x180039a84`
- `0x18003a560`
- `0x18003ae80`
- `0x180046540`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022a84`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180022a5c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180022a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b00`

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
0x1800227e8  mov     [rsp+arg_8], rbx
0x1800227ed  mov     [rsp+arg_10], rbp
0x1800227f2  push    rsi
0x1800227f3  push    rdi
0x1800227f4  push    r12
0x1800227f6  push    r13
0x1800227f8  push    r14
0x1800227fa  sub     rsp, 240h
0x180022801  mov     rax, cs:__security_cookie
0x180022808  xor     rax, rsp
0x18002280b  mov     [rsp+268h+var_38], rax
0x180022813  mov     rdi, rcx
0x180022816  mov     rcx, cs:WPP_GLOBAL_Control
0x18002281d  lea     r13, WPP_GLOBAL_Control
0x180022824  cmp     rcx, r13
0x180022827  jz      short loc_180022847
0x180022829  test    dword ptr [rcx+1Ch], 100h
0x180022830  jz      short loc_180022847
0x180022832  mov     rcx, [rcx+10h]
0x180022836  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002283d  mov     edx, 42h ; 'B'
0x180022842  call    WPP_SF_
0x180022847  lea     rcx, [rdi+8]; this
0x18002284b  call    ?LoadHttpApi@DelayLoadHttpApi@@QEAAJXZ; DelayLoadHttpApi::LoadHttpApi(void)
0x180022850  mov     ebx, eax
0x180022852  mov     r12d, 1
0x180022858  test    eax, eax
0x18002285a  jns     short loc_18002289A
0x18002285c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022863  cmp     rcx, r13
0x180022866  jz      loc_180022B94
0x18002286c  test    [rcx+1Ch], r12b
0x180022870  jz      loc_180022B60
0x180022876  mov     rcx, [rcx+10h]
0x18002287a  lea     edx, [r12+42h]
0x18002287f  mov     r9d, eax
0x180022882  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022889  call    WPP_SF_d
0x18002288e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022895  jmp     loc_180022B60
0x18002289a  mov     ecx, cs:dword_1800681C8
0x1800228a0  xor     r8d, r8d
0x1800228a3  mov     rax, [rdi+18h]
0x1800228a7  mov     edx, r12d
0x1800228aa  xor     r14d, r14d
0x1800228ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228b2  mov     ebx, eax
0x1800228b4  test    eax, eax
0x1800228b6  jz      short loc_1800228F9
0x1800228b8  xor     ebp, ebp
0x1800228ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228c1  cmp     rcx, r13
0x1800228c4  jz      short loc_1800228E9
0x1800228c6  test    [rcx+1Ch], r12b
0x1800228ca  jz      short loc_1800228E9
0x1800228cc  lea     edx, [rbp+44h]
0x1800228cf  mov     rcx, [rcx+10h]
0x1800228d3  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800228da  mov     r9d, ebx
0x1800228dd  call    WPP_SF_d
0x1800228e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800228e9  test    ebx, ebx
0x1800228eb  jle     loc_180022A02
0x1800228f1  movzx   ebx, bx
0x1800228f4  jmp     loc_1800229FA
0x1800228f9  mov     rax, [rdi+20h]
0x1800228fd  lea     rcx, [rdi+78h]
0x180022901  xor     edx, edx
0x180022903  mov     ebp, r12d
0x180022906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002290b  mov     ebx, eax
0x18002290d  test    eax, eax
0x18002290f  jz      short loc_18002292D
0x180022911  mov     rcx, cs:WPP_GLOBAL_Control
0x180022918  cmp     rcx, r13
0x18002291b  jz      short loc_1800228E9
0x18002291d  test    dword ptr [rcx+1Ch], 100h
0x180022924  jz      short loc_1800228E9
0x180022926  mov     edx, 45h ; 'E'
0x18002292b  jmp     short loc_1800228CF
0x18002292d  xor     edx, edx; Val
0x18002292f  lea     rcx, [rsp+268h+pszDest]; void *
0x180022934  mov     r8d, 1FEh; Size
0x18002293a  mov     r14d, r12d
0x18002293d  call    memset_0
0x180022942  mov     r9, [rdi+98h]
0x180022949  lea     rcx, [rsp+268h+pszDest]; pszDest
0x18002294e  mov     r8d, [rdi+0A0h]
0x180022955  mov     edx, 0FFh; cchDest
0x18002295a  call    ?CalculateFullPrefixW@@YAJPEAGKZZ; CalculateFullPrefixW(ushort *,ulong,...)
0x18002295f  mov     ebx, eax
0x180022961  test    eax, eax
0x180022963  jz      short loc_18002299D
0x180022965  mov     rcx, cs:WPP_GLOBAL_Control
0x18002296c  cmp     rcx, r13
0x18002296f  jz      loc_180022A00
0x180022975  test    [rcx+1Ch], r12b
0x180022979  jz      loc_180022A00
0x18002297f  mov     rcx, [rcx+10h]
0x180022983  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x18002298a  mov     edx, 46h ; 'F'
0x18002298f  call    WPP_SF_
0x180022994  mov     rcx, cs:WPP_GLOBAL_Control
0x18002299b  jmp     short loc_180022A00
0x18002299d  mov     rcx, [rdi+78h]
0x1800229a1  lea     rdx, [rsp+268h+pszDest]
0x1800229a6  mov     rax, [rdi+30h]
0x1800229aa  xor     r8d, r8d
0x1800229ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800229b2  mov     esi, eax
0x1800229b4  test    eax, eax
0x1800229b6  jz      short loc_180022A16
0x1800229b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229bf  cmp     rcx, r13
0x1800229c2  jz      short loc_1800229EF
0x1800229c4  test    [rcx+1Ch], r12b
0x1800229c8  jz      short loc_1800229EF
0x1800229ca  mov     rcx, [rcx+10h]
0x1800229ce  lea     r9, [rsp+268h+pszDest]
0x1800229d3  mov     edx, 47h ; 'G'
0x1800229d8  mov     [rsp+268h+dwCreationFlags], eax
0x1800229dc  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x1800229e3  call    WPP_SF_Sd
0x1800229e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800229ef  test    esi, esi
0x1800229f1  jg      short loc_1800229F7
0x1800229f3  mov     ebx, esi
0x1800229f5  jmp     short loc_180022A00
0x1800229f7  movzx   ebx, si
0x1800229fa  or      ebx, 80070000h
0x180022a00  test    ebx, ebx
0x180022a02  jns     loc_180022B5C
0x180022a08  test    r14d, r14d
0x180022a0b  jnz     loc_180022AF5
0x180022a11  jmp     loc_180022B15
0x180022a16  mov     rcx, [rdi+98h]
0x180022a1d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022a21  inc     rax
0x180022a24  cmp     byte ptr [rcx+rax], 0
0x180022a28  jnz     short loc_180022A21
0x180022a2a  cmp     dword ptr [rdi+80h], 0
0x180022a31  mov     [rdi+0B0h], eax
0x180022a37  jnz     loc_180022B94
0x180022a3d  mov     [rsp+268h+lpThreadId], 0; lpThreadId
0x180022a46  lea     r8, ?DoReceiveRequestHeadersStub@BaseHttpListener@@CAKPEAX@Z; lpStartAddress
0x180022a4d  mov     r9, rdi; lpParameter
0x180022a50  mov     [rsp+268h+dwCreationFlags], 0; dwCreationFlags
0x180022a58  xor     edx, edx; dwStackSize
0x180022a5a  xor     ecx, ecx; lpThreadAttributes
0x180022a5c  call    cs:__imp_CreateThread
0x180022a62  mov     [rdi+130h], rax
0x180022a69  test    rax, rax
0x180022a6c  jnz     loc_180022B85
0x180022a72  mov     rax, cs:WPP_GLOBAL_Control
0x180022a79  cmp     rax, r13
0x180022a7c  jz      short loc_180022AA9
0x180022a7e  test    [rax+1Ch], r12b
0x180022a82  jz      short loc_180022AA9
0x180022a84  call    cs:__imp_GetLastError
0x180022a8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180022a91  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022a98  mov     edx, 48h ; 'H'
0x180022a9d  mov     r9d, eax
0x180022aa0  mov     rcx, [rcx+10h]
0x180022aa4  call    WPP_SF_d
0x180022aa9  mov     rcx, [rdi+78h]
0x180022aad  lea     rdx, [rsp+268h+pszDest]
0x180022ab2  mov     rax, [rdi+40h]
0x180022ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022abb  test    eax, eax
0x180022abd  jz      short loc_180022AE9
0x180022abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ac6  cmp     rcx, r13
0x180022ac9  jz      short loc_180022AF0
0x180022acb  test    [rcx+1Ch], r12b
0x180022acf  jz      short loc_180022AF0
0x180022ad1  mov     rcx, [rcx+10h]
0x180022ad5  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022adc  mov     edx, 49h ; 'I'
0x180022ae1  mov     r9d, eax
0x180022ae4  call    WPP_SF_d
0x180022ae9  mov     rcx, cs:WPP_GLOBAL_Control
0x180022af0  mov     ebx, 80004005h
0x180022af5  cmp     qword ptr [rdi+78h], 0
0x180022afa  jz      short loc_180022B15
0x180022afc  mov     rcx, [rdi+78h]; hObject
0x180022b00  call    cs:__imp_CloseHandle
0x180022b06  mov     qword ptr [rdi+78h], 0
0x180022b0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b15  test    ebp, ebp
0x180022b17  jz      short loc_180022B5C
0x180022b19  mov     rax, [rdi+38h]
0x180022b1d  xor     edx, edx
0x180022b1f  mov     ecx, r12d
0x180022b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b27  test    eax, eax
0x180022b29  jz      short loc_180022B55
0x180022b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b32  cmp     rcx, r13
0x180022b35  jz      short loc_180022B5C
0x180022b37  test    [rcx+1Ch], r12b
0x180022b3b  jz      short loc_180022B5C
0x180022b3d  mov     rcx, [rcx+10h]
0x180022b41  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022b48  mov     edx, 4Ah ; 'J'
0x180022b4d  mov     r9d, eax
0x180022b50  call    WPP_SF_d
0x180022b55  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b5c  test    ebx, ebx
0x180022b5e  jz      short loc_180022B94
0x180022b60  cmp     rcx, r13
0x180022b63  jz      short loc_180022B94
0x180022b65  test    [rcx+1Ch], r12b
0x180022b69  jz      short loc_180022B94
0x180022b6b  mov     rcx, [rcx+10h]
0x180022b6f  lea     r8, WPP_44b0d7d673cb3f4de7293d8dcb8cb2f1_Traceguids
0x180022b76  mov     edx, 4Bh ; 'K'
0x180022b7b  mov     r9d, ebx
0x180022b7e  call    WPP_SF_d
0x180022b83  jmp     short loc_180022B94
0x180022b85  mov     rcx, rdi; this
0x180022b88  call    ?IncrThreadCount@BaseHttpListener@@IEAAXXZ; BaseHttpListener::IncrThreadCount(void)
0x180022b8d  mov     [rdi+80h], r12d
0x180022b94  mov     eax, ebx
0x180022b96  mov     rcx, [rsp+268h+var_38]
0x180022b9e  xor     rcx, rsp; StackCookie
0x180022ba1  call    __security_check_cookie
0x180022ba6  lea     r11, [rsp+268h+var_28]
0x180022bae  mov     rbx, [r11+38h]
0x180022bb2  mov     rbp, [r11+40h]
0x180022bb6  mov     rsp, r11
0x180022bb9  pop     r14
0x180022bbb  pop     r13
0x180022bbd  pop     r12
0x180022bbf  pop     rdi
0x180022bc0  pop     rsi
0x180022bc1  retn
```
