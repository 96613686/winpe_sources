# CVssRegistryValueIterator::GetCurrentValueType(void)

- ea: `0x14000c0a0`
- end: `0x14000c28f`
- name: `?GetCurrentValueType@CVssRegistryValueIterator@@QEAAKXZ`
- size: `495`
- prototype: `unsigned int __fastcall(CVssRegistryValueIterator *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000c84c`
- `0x14002b160`

## callees

- `0x14000c0a0`
- `0x14000dcd0`
- `0x1400137c0`
- `0x140013cb0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000c137`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14000c137`
- `VssTrace!__imp_VssTraceMessage` at `0x14000c284`
- `VssTrace!__imp_VssTraceMessage` at `0x14000c284`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000c21d`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14000c21d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000c17b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000c17b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000c207`

## string_xrefs

- `0x14000c0c5`: `CVssRegistryValueIterator::GetCurrentValueType`
- `0x14000c0ba`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssRegistryValueIterator::GetCurrentValueType(CVssRegistryValueIterator *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 i; // rbx
  void *v5; // rcx
  unsigned int v6; // ebx
  int v8; // eax
  unsigned __int64 v9; // [rsp+50h] [rbp-B0h] BYREF
  int v10; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v11; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v12; // [rsp+68h] [rbp-98h]
  unsigned int v13; // [rsp+70h] [rbp-90h]
  int v14; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v15; // [rsp+78h] [rbp-88h]
  unsigned int v16; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v18; // [rsp+88h] [rbp-78h]
  __int128 v19; // [rsp+90h] [rbp-70h]
  __int128 v20; // [rsp+A0h] [rbp-60h]
  __int64 v21; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v22; // [rsp+C0h] [rbp-40h]
  const wchar_t *v23; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v24; // [rsp+D0h] [rbp-30h]
  int v25; // [rsp+D8h] [rbp-28h]
  int v26; // [rsp+DCh] [rbp-24h]
  int v27; // [rsp+E0h] [rbp-20h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v29; // [rsp+160h] [rbp+60h]
  __int64 v30; // [rsp+180h] [rbp+80h] BYREF

  v22 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v23 = L"CVssRegistryValueIterator::GetCurrentValueType";
  v24 = L"REGREGSC";
  v25 = 887;
  v26 = 11;
  v27 = 255;
  v29 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v10 = 0;
  v15 = L"CVssRegistryValueIterator::GetCurrentValueType";
  v11 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v12 = L"REGREGSC";
  v13 = 887;
  v14 = 11;
  TickCount = GetTickCount();
  v18 = 255;
  v9 = 0xFFFFFFFF00000000uLL;
  v21 = 0;
  v19 = 0;
  v20 = 0;
  v30 = 0;
  if ( (int)VssGetTracingContextPerThread(&v30) >= 0 )
  {
    v8 = VssSetTracingContextPerThread(&v9);
    v2 = v21;
    if ( v8 >= 0 )
      v2 = v30;
    v21 = v2;
  }
  else
  {
    v2 = v21;
  }
  if ( v2 )
    v16 = *(_DWORD *)(v2 + 48) + 1;
  else
    v16 = 0;
  v3 = 160;
  if ( v18 != 255 )
    v3 = v18;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v9) )
    VssTraceMessage(v11, v12, v13, v16, v14, v15, L"ENTER", v3, 0);
  if ( HIBYTE(v29) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v5 = pv[i];
      if ( v5 )
      {
        CoTaskMemFree(v5);
        pv[i] = 0;
      }
    }
  }
  CVssRegistryValueIterator::ReadCurrentValueDetails(this);
  v6 = *((_DWORD *)this + 4);
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v9);
  return v6;
}

```

## disassembly

```asm
0x14000c0a0  mov     [rsp-8+arg_8], rbx
0x14000c0a5  mov     [rsp-8+arg_10], rdi
0x14000c0aa  push    rbp
0x14000c0ab  lea     rbp, [rsp-70h]
0x14000c0b0  sub     rsp, 170h
0x14000c0b7  mov     rdi, rcx
0x14000c0ba  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000c0c1  mov     [rbp+70h+var_B0], rax
0x14000c0c5  lea     rax, aCvssregistryva_2; "CVssRegistryValueIterator::GetCurrentVa"...
0x14000c0cc  mov     [rbp+70h+var_A8], rax
0x14000c0d0  lea     rax, aRegregsc; "REGREGSC"
0x14000c0d7  mov     [rbp+70h+var_A0], rax
0x14000c0db  mov     [rbp+70h+var_98], 377h
0x14000c0e2  mov     [rbp+70h+var_94], 0Bh
0x14000c0e9  mov     [rbp+70h+var_90], 0FFh
0x14000c0f0  mov     [rbp+70h+var_10], 1000000h
0x14000c0f7  xor     edx, edx; Val
0x14000c0f9  lea     r8d, [rdx+78h]; Size
0x14000c0fd  lea     rcx, [rbp+70h+pv]; void *
0x14000c101  call    memset_0
0x14000c106  mov     [rsp+170h+var_118], 0
0x14000c10e  mov     rax, [rbp+70h+var_A8]
0x14000c112  mov     [rsp+170h+var_F8], rax
0x14000c117  mov     rax, [rbp+70h+var_B0]
0x14000c11b  mov     [rsp+170h+var_110], rax
0x14000c120  mov     rax, [rbp+70h+var_A0]
0x14000c124  mov     [rsp+170h+var_108], rax
0x14000c129  mov     eax, [rbp+70h+var_98]
0x14000c12c  mov     [rsp+170h+var_100], eax
0x14000c130  mov     eax, [rbp+70h+var_94]
0x14000c133  mov     [rsp+170h+var_FC], eax
0x14000c137  call    cs:__imp_GetTickCount
0x14000c13d  mov     [rbp+70h+var_EC], eax
0x14000c140  mov     [rsp+170h+var_11C], 0FFFFFFFFh
0x14000c148  mov     eax, [rbp+70h+var_90]
0x14000c14b  mov     [rbp+70h+var_E8], eax
0x14000c14e  mov     [rsp+170h+var_120], 0
0x14000c156  mov     [rbp+70h+var_C0], 0
0x14000c15e  xorps   xmm0, xmm0
0x14000c161  movups  [rbp+70h+var_E0], xmm0
0x14000c165  movups  [rbp+70h+var_D0], xmm0
0x14000c169  mov     [rbp+70h+arg_0], 0
0x14000c174  lea     rcx, [rbp+70h+arg_0]
0x14000c17b  call    cs:__imp_VssGetTracingContextPerThread
0x14000c181  test    eax, eax
0x14000c183  jns     loc_14000C218
0x14000c189  mov     rcx, [rbp+70h+var_C0]
0x14000c18d  test    rcx, rcx
0x14000c190  jz      loc_14000C23A
0x14000c196  mov     eax, [rcx+30h]
0x14000c199  inc     eax
0x14000c19b  mov     [rbp+70h+var_F0], eax
0x14000c19e  mov     ebx, 0A0h
0x14000c1a3  cmp     [rbp+70h+var_E8], 0FFh
0x14000c1aa  cmovnz  ebx, [rbp+70h+var_E8]
0x14000c1ae  lea     rcx, [rsp+170h+var_120]; this
0x14000c1b3  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14000c1b8  test    eax, eax
0x14000c1ba  jnz     loc_14000C246
0x14000c1c0  cmp     byte ptr [rbp+70h+var_10+3], 0
0x14000c1c4  jz      short loc_14000C1DB
0x14000c1c6  xor     ebx, ebx
0x14000c1c8  mov     rcx, [rbp+rbx*8+70h+pv]; pv
0x14000c1cd  test    rcx, rcx
0x14000c1d0  jnz     short loc_14000C207
0x14000c1d2  inc     rbx
0x14000c1d5  cmp     rbx, 0Fh
0x14000c1d9  jnz     short loc_14000C1C8
0x14000c1db  mov     rcx, rdi; this
0x14000c1de  call    ?ReadCurrentValueDetails@CVssRegistryValueIterator@@AEAAXXZ; CVssRegistryValueIterator::ReadCurrentValueDetails(void)
0x14000c1e3  mov     ebx, [rdi+10h]
0x14000c1e6  lea     rcx, [rsp+170h+var_120]; this
0x14000c1eb  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14000c1f0  mov     eax, ebx
0x14000c1f2  lea     r11, [rsp+170h+var_s0]
0x14000c1fa  mov     rbx, [r11+18h]
0x14000c1fe  mov     rdi, [r11+20h]
0x14000c202  mov     rsp, r11
0x14000c205  pop     rbp
0x14000c206  retn
0x14000c207  call    cs:__imp_CoTaskMemFree
0x14000c20d  mov     [rbp+rbx*8+70h+pv], 0
0x14000c216  jmp     short loc_14000C1D2
0x14000c218  lea     rcx, [rsp+170h+var_120]
0x14000c21d  call    cs:__imp_VssSetTracingContextPerThread
0x14000c223  mov     rcx, [rbp+70h+var_C0]
0x14000c227  test    eax, eax
0x14000c229  cmovns  rcx, [rbp+70h+arg_0]
0x14000c231  mov     [rbp+70h+var_C0], rcx
0x14000c235  jmp     loc_14000C18D
0x14000c23a  mov     [rbp+70h+var_F0], 0
0x14000c241  jmp     loc_14000C19E
0x14000c246  mov     [rsp+170h+var_130], 0
0x14000c24f  mov     [rsp+170h+var_138], ebx
0x14000c253  lea     rax, aEnter; "ENTER"
0x14000c25a  mov     [rsp+170h+var_140], rax
0x14000c25f  mov     rax, [rsp+170h+var_F8]
0x14000c264  mov     [rsp+170h+var_148], rax
0x14000c269  mov     eax, [rsp+170h+var_FC]
0x14000c26d  mov     [rsp+170h+var_150], eax
0x14000c271  mov     r9d, [rbp+70h+var_F0]
0x14000c275  mov     r8d, [rsp+170h+var_100]
0x14000c27a  mov     rdx, [rsp+170h+var_108]
0x14000c27f  mov     rcx, [rsp+170h+var_110]
0x14000c284  call    cs:__imp_VssTraceMessage
0x14000c28a  jmp     loc_14000C1C0
```
