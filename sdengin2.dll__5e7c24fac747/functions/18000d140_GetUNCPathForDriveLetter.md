# GetUNCPathForDriveLetter

- ea: `0x18000d140`
- end: `0x18000d3c8`
- name: `GetUNCPathForDriveLetter`
- size: `648`
- prototype: `__int64 __fastcall(LPCWSTR lpLocalPath, CBsString *this)`
- caller_count: `3`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x18000b8c8`
- `0x18000cad0`
- `0x180012a8c`

## callees

- `0x180008240`
- `0x18000d140`
- `0x18006fe84`
- `0x18006ff8c`
- `0x180099484`
- `0x180099bdc`
- `0x18009a24c`
- `0x18009a3ac`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000d27e`
- `ole32!CoTaskMemFree` at `0x18000d38a`
- `ole32!CoTaskMemFree` at `0x18000d27e`
- `ole32!CoTaskMemFree` at `0x18000d38a`
- `ole32!CoTaskMemAlloc` at `0x18000d288`
- `ole32!CoTaskMemAlloc` at `0x18000d288`
- `MPR!WNetGetUniversalNameW` at `0x18000d268`
- `MPR!WNetGetUniversalNameW` at `0x18000d2b4`
- `MPR!WNetGetUniversalNameW` at `0x18000d268`
- `MPR!WNetGetUniversalNameW` at `0x18000d2b4`

## string_xrefs

- `0x18000d17e`: `GetUNCPathForDriveLetter`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v15, "GetUNCPathForDriveLetter", 2245, 1);
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
0x18000d140  mov     [rsp-8+arg_10], rbx
0x18000d145  mov     [rsp-8+arg_18], rsi
0x18000d14a  push    rbp
0x18000d14b  push    rdi
0x18000d14c  push    r12
0x18000d14e  push    r14
0x18000d150  push    r15
0x18000d152  lea     rbp, [rsp-37h]
0x18000d157  sub     rsp, 0F0h
0x18000d15e  mov     rax, cs:__security_cookie
0x18000d165  xor     rax, rsp
0x18000d168  mov     [rbp+57h+var_30], rax
0x18000d16c  mov     rbx, rdx
0x18000d16f  mov     rdi, rcx
0x18000d172  mov     r9d, 1; unsigned __int16
0x18000d178  mov     r8d, 8C5h; unsigned __int16
0x18000d17e  lea     rdx, aGetuncpathford; "GetUNCPathForDriveLetter"
0x18000d185  lea     rcx, [rsp+110h+var_E8]; this
0x18000d18a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000d18f  mov     r14d, 80h
0x18000d195  mov     r8d, r14d; Size
0x18000d198  xor     edx, edx; Val
0x18000d19a  lea     rcx, [rbp+57h+Buffer]; void *
0x18000d19e  call    memset_0
0x18000d1a3  xor     r15d, r15d
0x18000d1a6  mov     esi, r15d
0x18000d1a9  mov     [rsp+110h+BufferSize], r14d
0x18000d1ae  test    rbx, rbx
0x18000d1b1  jz      short loc_18000D1BB
0x18000d1b3  mov     rcx, rbx; this
0x18000d1b6  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x18000d1bb  mov     eax, 8CFh
0x18000d1c0  test    rdi, rdi
0x18000d1c3  jz      loc_18000D37A
0x18000d1c9  mov     [rsp+110h+var_E4], ax
0x18000d1ce  mov     eax, 8D0h
0x18000d1d3  test    rbx, rbx
0x18000d1d6  jz      loc_18000D37A
0x18000d1dc  mov     [rsp+110h+var_E8], r15d
0x18000d1e1  mov     [rsp+110h+var_E4], ax
0x18000d1e6  lea     rax, WPP_GLOBAL_Control
0x18000d1ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1f4  cmp     rcx, rax
0x18000d1f7  jz      short loc_18000D217
0x18000d1f9  test    byte ptr [rcx+1Ch], 2
0x18000d1fd  jz      short loc_18000D217
0x18000d1ff  mov     edx, 18h
0x18000d204  mov     r9, rdi
0x18000d207  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000d20e  mov     rcx, [rcx+10h]
0x18000d212  call    WPP_SF_S
0x18000d217  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d21b  inc     rax
0x18000d21e  cmp     [rdi+rax*2], r15w
0x18000d223  jnz     short loc_18000D21B
0x18000d225  cmp     rax, 1
0x18000d229  mov     eax, 8D4h
0x18000d22e  jbe     loc_18000D37A
0x18000d234  mov     [rsp+110h+var_E4], ax
0x18000d239  mov     eax, 8D5h
0x18000d23e  cmp     word ptr [rdi+2], 3Ah ; ':'
0x18000d243  jnz     loc_18000D37A
0x18000d249  lea     r14, [rbp+57h+Buffer]
0x18000d24d  mov     [rsp+110h+var_E8], r15d
0x18000d252  mov     [rsp+110h+var_E4], ax
0x18000d257  lea     r9, [rsp+110h+BufferSize]; lpBufferSize
0x18000d25c  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18000d260  mov     edx, 1; dwInfoLevel
0x18000d265  mov     rcx, rdi; lpLocalPath
0x18000d268  call    cs:__imp_WNetGetUniversalNameW
0x18000d26e  mov     r12d, 8DCh
0x18000d274  cmp     eax, 0EAh
0x18000d279  jnz     short loc_18000D2CF
0x18000d27b  mov     rcx, rsi; pv
0x18000d27e  call    cs:__imp_CoTaskMemFree
0x18000d284  mov     ecx, [rsp+110h+BufferSize]; cb
0x18000d288  call    cs:__imp_CoTaskMemAlloc
0x18000d28e  mov     rsi, rax
0x18000d291  test    rax, rax
0x18000d294  jz      short loc_18000D2BC
0x18000d296  mov     [rsp+110h+var_E8], r15d
0x18000d29b  mov     [rsp+110h+var_E4], r12w
0x18000d2a1  mov     r14, rax
0x18000d2a4  lea     r9, [rsp+110h+BufferSize]; lpBufferSize
0x18000d2a9  mov     r8, rax; lpBuffer
0x18000d2ac  mov     edx, 1; dwInfoLevel
0x18000d2b1  mov     rcx, rdi; lpLocalPath
0x18000d2b4  call    cs:__imp_WNetGetUniversalNameW
0x18000d2ba  jmp     short loc_18000D274
0x18000d2bc  mov     [rsp+110h+var_E8], 8007000Eh
0x18000d2c4  mov     [rsp+110h+var_E2], r12w
0x18000d2ca  jmp     loc_18000D387
0x18000d2cf  test    eax, eax
0x18000d2d1  jle     short loc_18000D2DB
0x18000d2d3  movzx   eax, ax
0x18000d2d6  or      eax, 80070000h
0x18000d2db  mov     [rsp+110h+var_E8], eax
0x18000d2df  test    eax, eax
0x18000d2e1  mov     eax, 8E1h
0x18000d2e6  js      loc_18000D382
0x18000d2ec  mov     [rsp+110h+var_E4], ax
0x18000d2f1  mov     rdx, [r14]; unsigned __int16 *
0x18000d2f4  mov     rcx, rbx; this
0x18000d2f7  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18000d2fc  mov     [rsp+110h+var_E8], eax
0x18000d300  test    eax, eax
0x18000d302  mov     eax, 8E3h
0x18000d307  js      short loc_18000D382
0x18000d309  mov     [rsp+110h+var_E4], ax
0x18000d30e  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000d313  mov     rcx, rbx; this
0x18000d316  call    ?Trailing@CBsString@@QEAAJG@Z; CBsString::Trailing(ushort)
0x18000d31b  mov     [rsp+110h+var_E8], eax
0x18000d31f  test    eax, eax
0x18000d321  mov     eax, 8E4h
0x18000d326  js      short loc_18000D382
0x18000d328  mov     [rsp+110h+var_E4], ax
0x18000d32d  mov     rcx, rbx; this
0x18000d330  call    ?AntiCanonicalize@CBsString@@QEAAJXZ; CBsString::AntiCanonicalize(void)
0x18000d335  mov     [rsp+110h+var_E8], eax
0x18000d339  test    eax, eax
0x18000d33b  mov     eax, 8E5h
0x18000d340  js      short loc_18000D382
0x18000d342  mov     [rsp+110h+var_E4], ax
0x18000d347  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d34e  lea     rax, WPP_GLOBAL_Control
0x18000d355  cmp     rcx, rax
0x18000d358  jz      short loc_18000D387
0x18000d35a  test    byte ptr [rcx+1Ch], 2
0x18000d35e  jz      short loc_18000D387
0x18000d360  mov     edx, 19h
0x18000d365  mov     r9, rbx
0x18000d368  lea     r8, WPP_5c877cbd96cc3be76668cfb840d6ca07_Traceguids
0x18000d36f  mov     rcx, [rcx+10h]
0x18000d373  call    WPP_SF_S
0x18000d378  jmp     short loc_18000D387
0x18000d37a  mov     [rsp+110h+var_E8], 80070057h
0x18000d382  mov     [rsp+110h+var_E2], ax
0x18000d387  mov     rcx, rsi; pv
0x18000d38a  call    cs:__imp_CoTaskMemFree
0x18000d390  mov     ebx, [rsp+110h+var_E8]
0x18000d394  lea     rcx, [rsp+110h+var_E8]; this
0x18000d399  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000d39e  mov     eax, ebx
0x18000d3a0  mov     rcx, [rbp+57h+var_30]
0x18000d3a4  xor     rcx, rsp; StackCookie
0x18000d3a7  call    __security_check_cookie
0x18000d3ac  lea     r11, [rsp+110h+var_20]
0x18000d3b4  mov     rbx, [r11+40h]
0x18000d3b8  mov     rsi, [r11+48h]
0x18000d3bc  mov     rsp, r11
0x18000d3bf  pop     r15
0x18000d3c1  pop     r14
0x18000d3c3  pop     r12
0x18000d3c5  pop     rdi
0x18000d3c6  pop     rbp
0x18000d3c7  retn
```
