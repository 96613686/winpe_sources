# CVssCoordinator::PreFreezeContext(void)

- ea: `0x140007060`
- end: `0x140007249`
- name: `?PreFreezeContext@CVssCoordinator@@AEAAXXZ`
- size: `489`
- prototype: `void __fastcall(CVssCoordinator *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004690`
- `0x140005050`
- `0x1400844c0`
- `0x140085360`

## callees

- `0x140007060`
- `0x1400137c0`
- `0x140013cb0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400070f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400070f7`
- `VssTrace!__imp_VssTraceMessage` at `0x14000723e`
- `VssTrace!__imp_VssTraceMessage` at `0x14000723e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400071d7`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400071d7`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000713b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14000713b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400071c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400071c1`

## pseudocode

```c
void __fastcall CVssCoordinator::PreFreezeContext(CVssCoordinator *this)
{
  __int64 v2; // rcx
  int v3; // ebx
  __int64 i; // rbx
  void *v5; // rcx
  int v6; // eax
  unsigned __int64 v7; // [rsp+50h] [rbp-B0h] BYREF
  int v8; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v9; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v10; // [rsp+68h] [rbp-98h]
  unsigned int v11; // [rsp+70h] [rbp-90h]
  int v12; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v13; // [rsp+78h] [rbp-88h]
  unsigned int v14; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v16; // [rsp+88h] [rbp-78h]
  __int128 v17; // [rsp+90h] [rbp-70h]
  __int128 v18; // [rsp+A0h] [rbp-60h]
  __int64 v19; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v20; // [rsp+C0h] [rbp-40h]
  const wchar_t *v21; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v22; // [rsp+D0h] [rbp-30h]
  int v23; // [rsp+D8h] [rbp-28h]
  int v24; // [rsp+DCh] [rbp-24h]
  int v25; // [rsp+E0h] [rbp-20h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v27; // [rsp+160h] [rbp+60h]
  __int64 v28; // [rsp+180h] [rbp+80h] BYREF

  v23 = 2718;
  v20 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v24 = 1;
  v21 = L"CVssCoordinator::PreFreezeContext";
  v25 = 255;
  v22 = L"CORCOORC";
  v27 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v13 = L"CVssCoordinator::PreFreezeContext";
  v9 = L"base\\stor\\vss\\modules\\coord\\src\\coord.cxx";
  v10 = L"CORCOORC";
  v11 = 2718;
  v12 = 1;
  v8 = 0;
  TickCount = GetTickCount();
  v16 = 255;
  v7 = 0xFFFFFFFF00000000uLL;
  v19 = 0;
  v17 = 0;
  v28 = 0;
  v18 = 0;
  if ( (int)VssGetTracingContextPerThread(&v28) >= 0 )
  {
    v6 = VssSetTracingContextPerThread(&v7);
    v2 = v19;
    if ( v6 >= 0 )
      v2 = v28;
    v19 = v2;
  }
  else
  {
    v2 = v19;
  }
  if ( v2 )
    v14 = *(_DWORD *)(v2 + 48) + 1;
  else
    v14 = 0;
  v3 = 160;
  if ( v16 != 255 )
    v3 = v16;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v7) )
    VssTraceMessage(v9, v10, v11, v14, v12, v13, L"ENTER", v3, 0);
  if ( HIBYTE(v27) )
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
  *((_BYTE *)this + 157) = 1;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v7);
}

```

## disassembly

```asm
0x140007060  mov     [rsp-8+arg_8], rbx
0x140007065  mov     [rsp-8+arg_10], rdi
0x14000706a  push    rbp
0x14000706b  lea     rbp, [rsp-70h]
0x140007070  sub     rsp, 170h
0x140007077  lea     rax, aBaseStorVssMod_14; "base\\stor\\vss\\modules\\coord\\src\\c"...
0x14000707e  mov     [rbp+70h+var_98], 0A9Eh
0x140007085  mov     [rbp+70h+var_B0], rax
0x140007089  xor     edx, edx; Val
0x14000708b  lea     rax, aCvsscoordinato_13; "CVssCoordinator::PreFreezeContext"
0x140007092  mov     [rbp+70h+var_94], 1
0x140007099  mov     [rbp+70h+var_A8], rax
0x14000709d  mov     rdi, rcx
0x1400070a0  lea     rax, aCorcoorc; "CORCOORC"
0x1400070a7  mov     [rbp+70h+var_90], 0FFh
0x1400070ae  lea     r8d, [rdx+78h]; Size
0x1400070b2  mov     [rbp+70h+var_A0], rax
0x1400070b6  lea     rcx, [rbp+70h+pv]; void *
0x1400070ba  mov     [rbp+70h+var_10], 1000000h
0x1400070c1  call    memset_0
0x1400070c6  mov     rax, [rbp+70h+var_A8]
0x1400070ca  mov     [rsp+170h+var_F8], rax
0x1400070cf  mov     rax, [rbp+70h+var_B0]
0x1400070d3  mov     [rsp+170h+var_110], rax
0x1400070d8  mov     rax, [rbp+70h+var_A0]
0x1400070dc  mov     [rsp+170h+var_108], rax
0x1400070e1  mov     eax, [rbp+70h+var_98]
0x1400070e4  mov     [rsp+170h+var_100], eax
0x1400070e8  mov     eax, [rbp+70h+var_94]
0x1400070eb  mov     [rsp+170h+var_FC], eax
0x1400070ef  mov     [rsp+170h+var_118], 0
0x1400070f7  call    cs:__imp_GetTickCount
0x1400070fd  xorps   xmm0, xmm0
0x140007100  mov     [rsp+170h+var_11C], 0FFFFFFFFh
0x140007108  mov     [rbp+70h+var_EC], eax
0x14000710b  lea     rcx, [rbp+70h+arg_0]
0x140007112  mov     eax, [rbp+70h+var_90]
0x140007115  mov     [rbp+70h+var_E8], eax
0x140007118  mov     [rsp+170h+var_120], 0
0x140007120  mov     [rbp+70h+var_C0], 0
0x140007128  movups  [rbp+70h+var_E0], xmm0
0x14000712c  mov     [rbp+70h+arg_0], 0
0x140007137  movups  [rbp+70h+var_D0], xmm0
0x14000713b  call    cs:__imp_VssGetTracingContextPerThread
0x140007141  test    eax, eax
0x140007143  jns     loc_1400071D2
0x140007149  mov     rcx, [rbp+70h+var_C0]
0x14000714d  test    rcx, rcx
0x140007150  jz      loc_1400071F4
0x140007156  mov     eax, [rcx+30h]
0x140007159  inc     eax
0x14000715b  mov     [rbp+70h+var_F0], eax
0x14000715e  cmp     [rbp+70h+var_E8], 0FFh
0x140007165  lea     rcx, [rsp+170h+var_120]; this
0x14000716a  mov     ebx, 0A0h
0x14000716f  cmovnz  ebx, [rbp+70h+var_E8]
0x140007173  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x140007178  test    eax, eax
0x14000717a  jnz     loc_140007200
0x140007180  cmp     byte ptr [rbp+70h+var_10+3], 0
0x140007184  jz      short loc_14000719B
0x140007186  xor     ebx, ebx
0x140007188  mov     rcx, [rbp+rbx*8+70h+pv]; pv
0x14000718d  test    rcx, rcx
0x140007190  jnz     short loc_1400071C1
0x140007192  inc     rbx
0x140007195  cmp     rbx, 0Fh
0x140007199  jnz     short loc_140007188
0x14000719b  lea     rcx, [rsp+170h+var_120]; this
0x1400071a0  mov     byte ptr [rdi+9Dh], 1
0x1400071a7  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400071ac  lea     r11, [rsp+170h+var_s0]
0x1400071b4  mov     rbx, [r11+18h]
0x1400071b8  mov     rdi, [r11+20h]
0x1400071bc  mov     rsp, r11
0x1400071bf  pop     rbp
0x1400071c0  retn
0x1400071c1  call    cs:__imp_CoTaskMemFree
0x1400071c7  mov     [rbp+rbx*8+70h+pv], 0
0x1400071d0  jmp     short loc_140007192
0x1400071d2  lea     rcx, [rsp+170h+var_120]
0x1400071d7  call    cs:__imp_VssSetTracingContextPerThread
0x1400071dd  mov     rcx, [rbp+70h+var_C0]
0x1400071e1  test    eax, eax
0x1400071e3  cmovns  rcx, [rbp+70h+arg_0]
0x1400071eb  mov     [rbp+70h+var_C0], rcx
0x1400071ef  jmp     loc_14000714D
0x1400071f4  mov     [rbp+70h+var_F0], 0
0x1400071fb  jmp     loc_14000715E
0x140007200  mov     r9d, [rbp+70h+var_F0]
0x140007204  lea     rax, aEnter; "ENTER"
0x14000720b  mov     r8d, [rsp+170h+var_100]
0x140007210  mov     rdx, [rsp+170h+var_108]
0x140007215  mov     rcx, [rsp+170h+var_110]
0x14000721a  mov     [rsp+170h+var_130], 0
0x140007223  mov     [rsp+170h+var_138], ebx
0x140007227  mov     [rsp+170h+var_140], rax
0x14000722c  mov     rax, [rsp+170h+var_F8]
0x140007231  mov     [rsp+170h+var_148], rax
0x140007236  mov     eax, [rsp+170h+var_FC]
0x14000723a  mov     [rsp+170h+var_150], eax
0x14000723e  call    cs:__imp_VssTraceMessage
0x140007244  jmp     loc_140007180
```
