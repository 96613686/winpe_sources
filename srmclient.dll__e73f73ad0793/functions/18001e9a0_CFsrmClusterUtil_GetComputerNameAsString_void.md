# CFsrmClusterUtil::GetComputerNameAsString(void)

- ea: `0x18001e9a0`
- end: `0x18001eb8e`
- name: `?GetComputerNameAsString@CFsrmClusterUtil@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `494`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800202b8`

## callees

- `0x180010bc4`
- `0x18001e9a0`
- `0x18006febc`
- `0x1800700b8`
- `0x180074048`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!GetComputerNameW` at `0x18001ea49`
- `KERNEL32!GetComputerNameW` at `0x18001ea49`
- `KERNEL32!GetLastError` at `0x18001ea53`
- `KERNEL32!GetLastError` at `0x18001ea53`

## string_xrefs

- `0x18001e9dc`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001e9e7`: `CFsrmClusterUtil::GetComputerNameAsString`
- `0x18001ea95`: `WARNING: failed to get the computer name [0x%08lx]`
- `0x18001eb03`: `- Computer name: '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall CFsrmClusterUtil::GetComputerNameAsString(_QWORD *a1)
{
  DWORD LastError; // ebx
  WCHAR *v3; // rdx
  __int64 v4; // r8
  DWORD nSize[6]; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v7; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v8; // [rsp+40h] [rbp-C0h]
  const wchar_t *v9; // [rsp+48h] [rbp-B8h]
  __int64 v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+58h] [rbp-A8h]
  _BYTE v12[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v13; // [rsp+C0h] [rbp-40h]
  _QWORD v14[4]; // [rsp+C8h] [rbp-38h] BYREF
  int v15; // [rsp+E8h] [rbp-18h]
  _BYTE v16[96]; // [rsp+F0h] [rbp-10h] BYREF
  int v17; // [rsp+150h] [rbp+50h]
  _QWORD v18[22]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Buffer[16]; // [rsp+210h] [rbp+110h] BYREF

  nSize[1] = HIDWORD(a1);
  v14[0] = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v14[1] = L"CFsrmClusterUtil::GetComputerNameAsString";
  v14[2] = L"CLUSUTLC";
  v14[3] = 708;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)v18,
    (const struct CSrmDebugInfo *)v14,
    (__int64)L"CFsrmClusterUtil::GetComputerNameAsString");
  nSize[0] = 15;
  if ( GetComputerNameW(Buffer, nSize) )
  {
    v7 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v8 = L"CFsrmClusterUtil::GetComputerNameAsString";
    v9 = L"CLUSUTLC";
    v10 = 718;
    v11 = 255;
    v13 = 0x1000000;
    memset_0(v12, 0, sizeof(v12));
    CSrmFunctionTracer::Trace(v18, &v7, L"- Computer name: '%s'", Buffer);
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    v4 = -1;
    do
      ++v4;
    while ( Buffer[v4] );
    v3 = Buffer;
  }
  else
  {
    LastError = GetLastError();
    v7 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v8 = L"CFsrmClusterUtil::GetComputerNameAsString";
    v9 = L"CLUSUTLC";
    v10 = 714;
    v11 = 255;
    v13 = 0x1000000;
    memset_0(v12, 0, sizeof(v12));
    CSrmFunctionTracer::Trace(v18, &v7, L"WARNING: failed to get the computer name [0x%08lx]", LastError);
    a1[3] = 7;
    a1[2] = 0;
    *(_WORD *)a1 = 0;
    v3 = L"<unknown>";
  }
  std::wstring::assign(a1, v3);
  v18[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v18);
  return a1;
}

```

## disassembly

```asm
0x18001e9a0  mov     [rsp-8+arg_8], rbx
0x18001e9a5  mov     [rsp-8+arg_10], rsi
0x18001e9aa  push    rbp
0x18001e9ab  push    rdi
0x18001e9ac  push    r12
0x18001e9ae  push    r14
0x18001e9b0  push    r15
0x18001e9b2  lea     rbp, [rsp-140h]
0x18001e9ba  sub     rsp, 240h
0x18001e9c1  mov     rax, cs:__security_cookie
0x18001e9c8  xor     rax, rsp
0x18001e9cb  mov     [rbp+160h+var_30], rax
0x18001e9d2  mov     rdi, rcx
0x18001e9d5  mov     qword ptr [rsp+260h+nSize], rcx
0x18001e9da  xor     esi, esi
0x18001e9dc  lea     r15, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001e9e3  mov     [rbp+160h+var_198], r15
0x18001e9e7  lea     r14, aCfsrmclusterut_11; "CFsrmClusterUtil::GetComputerNameAsStri"...
0x18001e9ee  mov     [rbp+160h+var_190], r14
0x18001e9f2  lea     r12, aClusutlc; "CLUSUTLC"
0x18001e9f9  mov     [rbp+160h+var_188], r12
0x18001e9fd  mov     [rbp+160h+var_180], 2C4h
0x18001ea05  mov     [rbp+160h+var_178], 0FFh
0x18001ea0c  mov     [rbp+160h+var_110], 1000000h
0x18001ea13  lea     ebx, [rsi+60h]
0x18001ea16  mov     r8d, ebx; Size
0x18001ea19  xor     edx, edx; Val
0x18001ea1b  lea     rcx, [rbp+160h+var_170]; void *
0x18001ea1f  call    memset_0
0x18001ea24  mov     r8, r14
0x18001ea27  lea     rdx, [rbp+160h+var_198]
0x18001ea2b  lea     rcx, [rbp+160h+var_100]
0x18001ea2f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001ea34  nop
0x18001ea35  mov     [rsp+260h+nSize], 0Fh
0x18001ea3d  lea     rdx, [rsp+260h+nSize]; nSize
0x18001ea42  lea     rcx, [rbp+160h+Buffer]; lpBuffer
0x18001ea49  call    cs:__imp_GetComputerNameW
0x18001ea4f  test    eax, eax
0x18001ea51  jnz     short loc_18001EAC6
0x18001ea53  call    cs:__imp_GetLastError
0x18001ea59  mov     ebx, eax
0x18001ea5b  mov     [rsp+260h+var_228], r15
0x18001ea60  mov     [rsp+260h+var_220], r14
0x18001ea65  mov     [rsp+260h+var_218], r12
0x18001ea6a  mov     [rsp+260h+var_210], 2CAh
0x18001ea73  mov     [rsp+260h+var_208], 0FFh
0x18001ea7b  mov     [rbp+160h+var_1A0], 1000000h
0x18001ea82  xor     edx, edx; Val
0x18001ea84  lea     r8d, [rsi+60h]; Size
0x18001ea88  lea     rcx, [rsp+260h+var_200]; void *
0x18001ea8d  call    memset_0
0x18001ea92  mov     r9d, ebx
0x18001ea95  lea     r8, aWarningFailedT_2; "WARNING: failed to get the computer nam"...
0x18001ea9c  lea     rdx, [rsp+260h+var_228]
0x18001eaa1  lea     rcx, [rbp+160h+var_100]
0x18001eaa5  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001eaaa  mov     qword ptr [rdi+18h], 7
0x18001eab2  mov     [rdi+10h], rsi
0x18001eab6  mov     [rdi], si
0x18001eab9  lea     r8d, [rsi+9]
0x18001eabd  lea     rdx, aUnknown; "<unknown>"
0x18001eac4  jmp     short loc_18001EB43
0x18001eac6  mov     [rsp+260h+var_228], r15
0x18001eacb  mov     [rsp+260h+var_220], r14
0x18001ead0  mov     [rsp+260h+var_218], r12
0x18001ead5  mov     [rsp+260h+var_210], 2CEh
0x18001eade  mov     [rsp+260h+var_208], 0FFh
0x18001eae6  mov     [rbp+160h+var_1A0], 1000000h
0x18001eaed  mov     r8, rbx; Size
0x18001eaf0  xor     edx, edx; Val
0x18001eaf2  lea     rcx, [rsp+260h+var_200]; void *
0x18001eaf7  call    memset_0
0x18001eafc  lea     r9, [rbp+160h+Buffer]
0x18001eb03  lea     r8, aComputerNameS; "- Computer name: '%s'"
0x18001eb0a  lea     rdx, [rsp+260h+var_228]
0x18001eb0f  lea     rcx, [rbp+160h+var_100]
0x18001eb13  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001eb18  mov     qword ptr [rdi+18h], 7
0x18001eb20  mov     [rdi+10h], rsi
0x18001eb24  mov     [rdi], si
0x18001eb27  lea     rax, [rbp+160h+Buffer]
0x18001eb2e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001eb32  inc     r8
0x18001eb35  cmp     [rax+r8*2], si
0x18001eb3a  jnz     short loc_18001EB32
0x18001eb3c  lea     rdx, [rbp+160h+Buffer]; Src
0x18001eb43  mov     rcx, rdi; void *
0x18001eb46  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001eb4b  nop
0x18001eb4c  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001eb53  mov     [rbp+160h+var_100], rax
0x18001eb57  lea     rcx, [rbp+160h+var_100]; this
0x18001eb5b  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001eb60  mov     rax, rdi
0x18001eb63  mov     rcx, [rbp+160h+var_30]
0x18001eb6a  xor     rcx, rsp; StackCookie
0x18001eb6d  call    __security_check_cookie
0x18001eb72  lea     r11, [rsp+260h+var_20]
0x18001eb7a  mov     rbx, [r11+38h]
0x18001eb7e  mov     rsi, [r11+40h]
0x18001eb82  mov     rsp, r11
0x18001eb85  pop     r15
0x18001eb87  pop     r14
0x18001eb89  pop     r12
0x18001eb8b  pop     rdi
0x18001eb8c  pop     rbp
0x18001eb8d  retn
```
