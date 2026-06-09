# GetUNCPathForDriveLetter

- ea: `0x18000d564`
- end: `0x18000d80b`
- name: `GetUNCPathForDriveLetter`
- size: `679`
- prototype: `__int64 __fastcall(LPCWSTR lpLocalPath, CBsString *this)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000bc28`
- `0x18000cea8`
- `0x1800132f0`

## callees

- `0x1800083e4`
- `0x18000d564`
- `0x180072e08`
- `0x180072f14`
- `0x18009da98`
- `0x18009e234`
- `0x18009e904`
- `0x18009ea6c`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000d6a8`
- `ole32!CoTaskMemFree` at `0x18000d7c6`
- `ole32!CoTaskMemFree` at `0x18000d6a8`
- `ole32!CoTaskMemFree` at `0x18000d7c6`
- `ole32!CoTaskMemAlloc` at `0x18000d6b8`
- `ole32!CoTaskMemAlloc` at `0x18000d6b8`
- `MPR!WNetGetUniversalNameW` at `0x18000d68c`
- `MPR!WNetGetUniversalNameW` at `0x18000d6ea`
- `MPR!WNetGetUniversalNameW` at `0x18000d68c`
- `MPR!WNetGetUniversalNameW` at `0x18000d6ea`

## string_xrefs

- `0x18000d5a2`: `GetUNCPathForDriveLetter`

## pseudocode

```c
__int64 __fastcall GetUNCPathForDriveLetter(LPCWSTR lpLocalPath, CBsString *this)
{
  void *v4; // rsi
  __int16 v5; // ax
  unsigned __int64 v6; // rax
  bool v7; // cc
  const unsigned __int16 **v8; // r14
  signed int i; // eax
  void *v10; // rax
  bool v11; // sf
  unsigned int v12; // ebx
  DWORD BufferSize; // [rsp+20h] [rbp-99h] BYREF
  int v15; // [rsp+28h] [rbp-91h] BYREF
  __int16 v16; // [rsp+2Ch] [rbp-8Dh]
  __int16 v17; // [rsp+2Eh] [rbp-8Bh]
  _BYTE Buffer[128]; // [rsp+60h] [rbp-59h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "GetUNCPathForDriveLetter", 0x8C5u, 1u);
  memset_0(Buffer, 0, sizeof(Buffer));
  v4 = 0;
  BufferSize = 128;
  if ( this )
    CBsString::Empty(this);
  v5 = 2255;
  if ( !lpLocalPath )
    goto LABEL_26;
  v16 = 2255;
  v5 = 2256;
  if ( !this )
    goto LABEL_26;
  v15 = 0;
  v16 = 2256;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids, lpLocalPath);
  v6 = -1;
  do
    ++v6;
  while ( lpLocalPath[v6] );
  v7 = v6 <= 1;
  v5 = 2260;
  if ( v7 || (v16 = 2260, v5 = 2261, lpLocalPath[1] != 58) )
  {
LABEL_26:
    v15 = -2147024809;
LABEL_27:
    v17 = v5;
    goto LABEL_28;
  }
  v8 = (const unsigned __int16 **)Buffer;
  v15 = 0;
  v16 = 2261;
  for ( i = WNetGetUniversalNameW(lpLocalPath, 1u, Buffer, &BufferSize);
        i == 234;
        i = WNetGetUniversalNameW(lpLocalPath, 1u, v10, &BufferSize) )
  {
    CoTaskMemFree(v4);
    v10 = CoTaskMemAlloc(BufferSize);
    v4 = v10;
    if ( !v10 )
    {
      v15 = -2147024882;
      v17 = 2268;
      goto LABEL_28;
    }
    v15 = 0;
    v16 = 2268;
    v8 = (const unsigned __int16 **)v10;
  }
  if ( i > 0 )
    i = (unsigned __int16)i | 0x80070000;
  v15 = i;
  v11 = i < 0;
  v5 = 2273;
  if ( v11 )
    goto LABEL_27;
  v16 = 2273;
  v15 = CBsString::Set(this, *v8);
  v5 = 2275;
  if ( v15 < 0 )
    goto LABEL_27;
  v16 = 2275;
  v15 = CBsString::Trailing(this, 0x5Cu);
  v5 = 2276;
  if ( v15 < 0 )
    goto LABEL_27;
  v16 = 2276;
  v15 = CBsString::AntiCanonicalize(this);
  v5 = 2277;
  if ( v15 < 0 )
    goto LABEL_27;
  v16 = 2277;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids, this);
LABEL_28:
  CoTaskMemFree(v4);
  v12 = v15;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v15);
  return v12;
}

```

## disassembly

```asm
0x18000d564  mov     [rsp-8+arg_10], rbx
0x18000d569  mov     [rsp-8+arg_18], rsi
0x18000d56e  push    rbp
0x18000d56f  push    rdi
0x18000d570  push    r12
0x18000d572  push    r14
0x18000d574  push    r15
0x18000d576  lea     rbp, [rsp-37h]
0x18000d57b  sub     rsp, 0F0h
0x18000d582  mov     rax, cs:__security_cookie
0x18000d589  xor     rax, rsp
0x18000d58c  mov     [rbp+57h+var_30], rax
0x18000d590  mov     rbx, rdx
0x18000d593  mov     rdi, rcx
0x18000d596  mov     r9d, 1; unsigned __int16
0x18000d59c  mov     r8d, 8C5h; unsigned __int16
0x18000d5a2  lea     rdx, aGetuncpathford; "GetUNCPathForDriveLetter"
0x18000d5a9  lea     rcx, [rsp+110h+var_E8]; this
0x18000d5ae  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d5b3  mov     r14d, 80h
0x18000d5b9  mov     r8d, r14d; Size
0x18000d5bc  xor     edx, edx; Val
0x18000d5be  lea     rcx, [rbp+57h+Buffer]; void *
0x18000d5c2  call    memset_0
0x18000d5c7  xor     r15d, r15d
0x18000d5ca  mov     esi, r15d
0x18000d5cd  mov     [rsp+110h+BufferSize], r14d
0x18000d5d2  test    rbx, rbx
0x18000d5d5  jz      short loc_18000D5DF
0x18000d5d7  mov     rcx, rbx; this
0x18000d5da  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18000d5df  mov     eax, 8CFh
0x18000d5e4  test    rdi, rdi
0x18000d5e7  jz      loc_18000D7B6
0x18000d5ed  mov     [rsp+110h+var_E4], ax
0x18000d5f2  mov     eax, 8D0h
0x18000d5f7  test    rbx, rbx
0x18000d5fa  jz      loc_18000D7B6
0x18000d600  mov     [rsp+110h+var_E8], r15d
0x18000d605  mov     [rsp+110h+var_E4], ax
0x18000d60a  lea     rax, WPP_GLOBAL_Control
0x18000d611  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d618  cmp     rcx, rax
0x18000d61b  jz      short loc_18000D63B
0x18000d61d  test    byte ptr [rcx+1Ch], 2
0x18000d621  jz      short loc_18000D63B
0x18000d623  mov     edx, 18h
0x18000d628  mov     r9, rdi
0x18000d62b  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000d632  mov     rcx, [rcx+10h]
0x18000d636  call    WPP_SF_S
0x18000d63b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d63f  inc     rax
0x18000d642  cmp     [rdi+rax*2], r15w
0x18000d647  jnz     short loc_18000D63F
0x18000d649  cmp     rax, 1
0x18000d64d  mov     eax, 8D4h
0x18000d652  jbe     loc_18000D7B6
0x18000d658  mov     [rsp+110h+var_E4], ax
0x18000d65d  mov     eax, 8D5h
0x18000d662  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18000d667  jnz     loc_18000D7B6
0x18000d66d  lea     r14, [rbp+57h+Buffer]
0x18000d671  mov     [rsp+110h+var_E8], r15d
0x18000d676  mov     [rsp+110h+var_E4], ax
0x18000d67b  lea     r9, [rsp+110h+BufferSize]; lpBufferSize
0x18000d680  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18000d684  mov     edx, 1; dwInfoLevel
0x18000d689  mov     rcx, rdi; lpLocalPath
0x18000d68c  call    cs:__imp_WNetGetUniversalNameW
0x18000d693  nop     dword ptr [rax+rax+00h]
0x18000d698  mov     r12d, 8DCh
0x18000d69e  cmp     eax, 0EAh
0x18000d6a3  jnz     short loc_18000D70B
0x18000d6a5  mov     rcx, rsi; pv
0x18000d6a8  call    cs:__imp_CoTaskMemFree
0x18000d6af  nop     dword ptr [rax+rax+00h]
0x18000d6b4  mov     ecx, [rsp+110h+BufferSize]; cb
0x18000d6b8  call    cs:__imp_CoTaskMemAlloc
0x18000d6bf  nop     dword ptr [rax+rax+00h]
0x18000d6c4  mov     rsi, rax
0x18000d6c7  test    rax, rax
0x18000d6ca  jz      short loc_18000D6F8
0x18000d6cc  mov     [rsp+110h+var_E8], r15d
0x18000d6d1  mov     [rsp+110h+var_E4], r12w
0x18000d6d7  mov     r14, rax
0x18000d6da  lea     r9, [rsp+110h+BufferSize]; lpBufferSize
0x18000d6df  mov     r8, rax; lpBuffer
0x18000d6e2  mov     edx, 1; dwInfoLevel
0x18000d6e7  mov     rcx, rdi; lpLocalPath
0x18000d6ea  call    cs:__imp_WNetGetUniversalNameW
0x18000d6f1  nop     dword ptr [rax+rax+00h]
0x18000d6f6  jmp     short loc_18000D69E
0x18000d6f8  mov     [rsp+110h+var_E8], 8007000Eh
0x18000d700  mov     [rsp+110h+var_E2], r12w
0x18000d706  jmp     loc_18000D7C3
0x18000d70b  test    eax, eax
0x18000d70d  jle     short loc_18000D717
0x18000d70f  movzx   eax, ax
0x18000d712  or      eax, 80070000h
0x18000d717  mov     [rsp+110h+var_E8], eax
0x18000d71b  test    eax, eax
0x18000d71d  mov     eax, 8E1h
0x18000d722  js      loc_18000D7BE
0x18000d728  mov     [rsp+110h+var_E4], ax
0x18000d72d  mov     rdx, [r14]; unsigned __int16 *
0x18000d730  mov     rcx, rbx; this
0x18000d733  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000d738  mov     [rsp+110h+var_E8], eax
0x18000d73c  test    eax, eax
0x18000d73e  mov     eax, 8E3h
0x18000d743  js      short loc_18000D7BE
0x18000d745  mov     [rsp+110h+var_E4], ax
0x18000d74a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000d74f  mov     rcx, rbx; this
0x18000d752  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000d757  mov     [rsp+110h+var_E8], eax
0x18000d75b  test    eax, eax
0x18000d75d  mov     eax, 8E4h
0x18000d762  js      short loc_18000D7BE
0x18000d764  mov     [rsp+110h+var_E4], ax
0x18000d769  mov     rcx, rbx; this
0x18000d76c  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18000d771  mov     [rsp+110h+var_E8], eax
0x18000d775  test    eax, eax
0x18000d777  mov     eax, 8E5h
0x18000d77c  js      short loc_18000D7BE
0x18000d77e  mov     [rsp+110h+var_E4], ax
0x18000d783  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d78a  lea     rax, WPP_GLOBAL_Control
0x18000d791  cmp     rcx, rax
0x18000d794  jz      short loc_18000D7C3
0x18000d796  test    byte ptr [rcx+1Ch], 2
0x18000d79a  jz      short loc_18000D7C3
0x18000d79c  mov     edx, 19h
0x18000d7a1  mov     r9, rbx
0x18000d7a4  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000d7ab  mov     rcx, [rcx+10h]
0x18000d7af  call    WPP_SF_S
0x18000d7b4  jmp     short loc_18000D7C3
0x18000d7b6  mov     [rsp+110h+var_E8], 80070057h
0x18000d7be  mov     [rsp+110h+var_E2], ax
0x18000d7c3  mov     rcx, rsi; pv
0x18000d7c6  call    cs:__imp_CoTaskMemFree
0x18000d7cd  nop     dword ptr [rax+rax+00h]
0x18000d7d2  mov     ebx, [rsp+110h+var_E8]
0x18000d7d6  lea     rcx, [rsp+110h+var_E8]; this
0x18000d7db  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d7e0  mov     eax, ebx
0x18000d7e2  mov     rcx, [rbp+57h+var_30]
0x18000d7e6  xor     rcx, rsp; StackCookie
0x18000d7e9  call    __security_check_cookie
0x18000d7ee  lea     r11, [rsp+110h+var_20]
0x18000d7f6  mov     rbx, [r11+40h]
0x18000d7fa  mov     rsi, [r11+48h]
0x18000d7fe  mov     rsp, r11
0x18000d801  pop     r15
0x18000d803  pop     r14
0x18000d805  pop     r12
0x18000d807  pop     rdi
0x18000d808  pop     rbp
0x18000d809  retn
```
