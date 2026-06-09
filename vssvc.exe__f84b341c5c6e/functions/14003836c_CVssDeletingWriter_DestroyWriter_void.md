# CVssDeletingWriter::DestroyWriter(void)

- ea: `0x14003836c`
- end: `0x140038550`
- name: `?DestroyWriter@CVssDeletingWriter@@SAXXZ`
- size: `484`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140037200`

## callees

- `0x1400137c0`
- `0x140013cb0`
- `0x14003836c`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400383fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400383fb`
- `VssTrace!__imp_VssTraceMessage` at `0x1400384de`
- `VssTrace!__imp_VssTraceMessage` at `0x1400384de`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003844e`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003844e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003843f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003843f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400384f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400384f6`

## string_xrefs

- `0x14003837e`: `base\stor\vss\modules\writers\deletewriter.cpp`
- `0x14003839d`: `CVssDeletingWriter::DestroyWriter`

## pseudocode

```c
void CVssDeletingWriter::DestroyWriter(void)
{
  int v0; // eax
  __int64 v1; // rcx
  int v2; // ebx
  __int64 i; // rbx
  void *v4; // rcx
  unsigned __int64 v5; // [rsp+50h] [rbp-B0h] BYREF
  int v6; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v7; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v8; // [rsp+68h] [rbp-98h]
  unsigned int v9; // [rsp+70h] [rbp-90h]
  int v10; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v11; // [rsp+78h] [rbp-88h]
  unsigned int v12; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v14; // [rsp+88h] [rbp-78h]
  __int128 v15; // [rsp+90h] [rbp-70h]
  __int128 v16; // [rsp+A0h] [rbp-60h]
  __int64 v17; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v18; // [rsp+C0h] [rbp-40h]
  const wchar_t *v19; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v20; // [rsp+D0h] [rbp-30h]
  int v21; // [rsp+D8h] [rbp-28h]
  int v22; // [rsp+DCh] [rbp-24h]
  int v23; // [rsp+E0h] [rbp-20h]
  LPVOID pv[15]; // [rsp+E8h] [rbp-18h] BYREF
  int v25; // [rsp+160h] [rbp+60h]
  __int64 v26; // [rsp+180h] [rbp+80h] BYREF

  v21 = 246;
  v18 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v22 = 4;
  v23 = 255;
  v19 = L"CVssDeletingWriter::DestroyWriter";
  v20 = L"WRTDELET";
  v25 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v11 = L"CVssDeletingWriter::DestroyWriter";
  v7 = L"base\\stor\\vss\\modules\\writers\\deletewriter.cpp";
  v8 = L"WRTDELET";
  v9 = 246;
  v10 = 4;
  v6 = 0;
  TickCount = GetTickCount();
  v14 = 255;
  v5 = 0xFFFFFFFF00000000uLL;
  v17 = 0;
  v15 = 0;
  v26 = 0;
  v16 = 0;
  if ( (int)VssGetTracingContextPerThread(&v26) < 0 )
  {
    v1 = v17;
  }
  else
  {
    v0 = VssSetTracingContextPerThread(&v5);
    v1 = v17;
    if ( v0 >= 0 )
      v1 = v26;
    v17 = v1;
  }
  if ( v1 )
    v12 = *(_DWORD *)(v1 + 48) + 1;
  else
    v12 = 0;
  v2 = 160;
  if ( v14 != 255 )
    v2 = v14;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v5) )
    VssTraceMessage(v7, v8, v9, v12, v10, v11, L"ENTER", v2, 0);
  if ( HIBYTE(v25) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v4 = pv[i];
      if ( v4 )
      {
        CoTaskMemFree(v4);
        pv[i] = 0;
      }
    }
  }
  if ( CVssDeletingWriter::m_instance )
  {
    (**(void (__fastcall ***)(CVssWriterEx *, __int64))CVssDeletingWriter::m_instance)(
      CVssDeletingWriter::m_instance,
      1);
    CVssDeletingWriter::m_instance = 0;
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v5);
}

```

## disassembly

```asm
0x14003836c  mov     [rsp-8+arg_8], rbx
0x140038371  push    rbp
0x140038372  lea     rbp, [rsp-70h]
0x140038377  sub     rsp, 170h
0x14003837e  lea     rax, aBaseStorVssMod_35; "base\\stor\\vss\\modules\\writers\\dele"...
0x140038385  mov     [rbp+70h+var_98], 0F6h
0x14003838c  mov     [rbp+70h+var_B0], rax
0x140038390  lea     rcx, [rbp+70h+pv]; void *
0x140038394  xor     edx, edx; Val
0x140038396  mov     [rbp+70h+var_94], 4
0x14003839d  lea     rax, aCvssdeletingwr_10; "CVssDeletingWriter::DestroyWriter"
0x1400383a4  mov     [rbp+70h+var_90], 0FFh
0x1400383ab  mov     [rbp+70h+var_A8], rax
0x1400383af  lea     rax, aWrtdelet; "WRTDELET"
0x1400383b6  mov     [rbp+70h+var_A0], rax
0x1400383ba  lea     r8d, [rdx+78h]; Size
0x1400383be  mov     [rbp+70h+var_10], 1000000h
0x1400383c5  call    memset_0
0x1400383ca  mov     rax, [rbp+70h+var_A8]
0x1400383ce  mov     [rsp+170h+var_F8], rax
0x1400383d3  mov     rax, [rbp+70h+var_B0]
0x1400383d7  mov     [rsp+170h+var_110], rax
0x1400383dc  mov     rax, [rbp+70h+var_A0]
0x1400383e0  mov     [rsp+170h+var_108], rax
0x1400383e5  mov     eax, [rbp+70h+var_98]
0x1400383e8  mov     [rsp+170h+var_100], eax
0x1400383ec  mov     eax, [rbp+70h+var_94]
0x1400383ef  mov     [rsp+170h+var_FC], eax
0x1400383f3  mov     [rsp+170h+var_118], 0
0x1400383fb  call    cs:__imp_GetTickCount
0x140038401  xorps   xmm0, xmm0
0x140038404  mov     [rsp+170h+var_11C], 0FFFFFFFFh
0x14003840c  mov     [rbp+70h+var_EC], eax
0x14003840f  lea     rcx, [rbp+70h+arg_0]
0x140038416  mov     eax, [rbp+70h+var_90]
0x140038419  mov     [rbp+70h+var_E8], eax
0x14003841c  mov     [rsp+170h+var_120], 0
0x140038424  mov     [rbp+70h+var_C0], 0
0x14003842c  movups  [rbp+70h+var_E0], xmm0
0x140038430  mov     [rbp+70h+arg_0], 0
0x14003843b  movups  [rbp+70h+var_D0], xmm0
0x14003843f  call    cs:__imp_VssGetTracingContextPerThread
0x140038445  test    eax, eax
0x140038447  js      short loc_140038468
0x140038449  lea     rcx, [rsp+170h+var_120]
0x14003844e  call    cs:__imp_VssSetTracingContextPerThread
0x140038454  mov     rcx, [rbp+70h+var_C0]
0x140038458  test    eax, eax
0x14003845a  cmovns  rcx, [rbp+70h+arg_0]
0x140038462  mov     [rbp+70h+var_C0], rcx
0x140038466  jmp     short loc_14003846C
0x140038468  mov     rcx, [rbp+70h+var_C0]
0x14003846c  test    rcx, rcx
0x14003846f  jz      short loc_14003847B
0x140038471  mov     eax, [rcx+30h]
0x140038474  inc     eax
0x140038476  mov     [rbp+70h+var_F0], eax
0x140038479  jmp     short loc_140038482
0x14003847b  mov     [rbp+70h+var_F0], 0
0x140038482  cmp     [rbp+70h+var_E8], 0FFh
0x140038489  lea     rcx, [rsp+170h+var_120]; this
0x14003848e  mov     ebx, 0A0h
0x140038493  cmovnz  ebx, [rbp+70h+var_E8]
0x140038497  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14003849c  test    eax, eax
0x14003849e  jz      short loc_1400384E4
0x1400384a0  mov     r9d, [rbp+70h+var_F0]
0x1400384a4  lea     rax, aEnter; "ENTER"
0x1400384ab  mov     r8d, [rsp+170h+var_100]
0x1400384b0  mov     rdx, [rsp+170h+var_108]
0x1400384b5  mov     rcx, [rsp+170h+var_110]
0x1400384ba  mov     [rsp+170h+var_130], 0
0x1400384c3  mov     [rsp+170h+var_138], ebx
0x1400384c7  mov     [rsp+170h+var_140], rax
0x1400384cc  mov     rax, [rsp+170h+var_F8]
0x1400384d1  mov     [rsp+170h+var_148], rax
0x1400384d6  mov     eax, [rsp+170h+var_FC]
0x1400384da  mov     [rsp+170h+var_150], eax
0x1400384de  call    cs:__imp_VssTraceMessage
0x1400384e4  cmp     byte ptr [rbp+70h+var_10+3], 0
0x1400384e8  jz      short loc_14003850E
0x1400384ea  xor     ebx, ebx
0x1400384ec  mov     rcx, [rbp+rbx*8+70h+pv]; pv
0x1400384f1  test    rcx, rcx
0x1400384f4  jz      short loc_140038505
0x1400384f6  call    cs:__imp_CoTaskMemFree
0x1400384fc  mov     [rbp+rbx*8+70h+pv], 0
0x140038505  inc     rbx
0x140038508  cmp     rbx, 0Fh
0x14003850c  jnz     short loc_1400384EC
0x14003850e  mov     rcx, cs:?m_instance@CVssDeletingWriter@@1PEAV1@EA; CVssDeletingWriter * CVssDeletingWriter::m_instance
0x140038515  test    rcx, rcx
0x140038518  jz      short loc_140038535
0x14003851a  mov     rax, [rcx]
0x14003851d  mov     edx, 1
0x140038522  mov     rax, [rax]
0x140038525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003852a  mov     cs:?m_instance@CVssDeletingWriter@@1PEAV1@EA, 0; CVssDeletingWriter * CVssDeletingWriter::m_instance
0x140038535  lea     rcx, [rsp+170h+var_120]; this
0x14003853a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003853f  mov     rbx, [rsp+170h+arg_8]
0x140038547  add     rsp, 170h
0x14003854e  pop     rbp
0x14003854f  retn
```
