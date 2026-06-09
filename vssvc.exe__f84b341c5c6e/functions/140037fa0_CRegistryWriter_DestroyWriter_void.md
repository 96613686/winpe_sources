# CRegistryWriter::DestroyWriter(void)

- ea: `0x140037fa0`
- end: `0x140038173`
- name: `?DestroyWriter@CRegistryWriter@@SAXXZ`
- size: `467`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140037200`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140037fa0`
- `0x14003817c`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003802f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003802f`
- `VssTrace!__imp_VssTraceMessage` at `0x140038112`
- `VssTrace!__imp_VssTraceMessage` at `0x140038112`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140038082`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140038082`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140038073`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140038073`

## string_xrefs

- `0x140037fbd`: `CRegistryWriter::DestroyWriter`
- `0x140037fb2`: `base\stor\vss\modules\writers\regwriter.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void CRegistryWriter::DestroyWriter(void)
{
  int v0; // eax
  __int64 v1; // rcx
  int v2; // ebx
  CRegistryWriter *v3; // rcx
  unsigned __int64 v4; // [rsp+50h] [rbp-B0h] BYREF
  int v5; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v6; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v7; // [rsp+68h] [rbp-98h]
  unsigned int v8; // [rsp+70h] [rbp-90h]
  int v9; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v10; // [rsp+78h] [rbp-88h]
  unsigned int v11; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  int v13; // [rsp+88h] [rbp-78h]
  __int128 v14; // [rsp+90h] [rbp-70h]
  __int128 v15; // [rsp+A0h] [rbp-60h]
  __int64 v16; // [rsp+B0h] [rbp-50h]
  _QWORD v17[3]; // [rsp+C0h] [rbp-40h] BYREF
  int v18; // [rsp+D8h] [rbp-28h]
  int v19; // [rsp+DCh] [rbp-24h]
  int v20; // [rsp+E0h] [rbp-20h]
  _BYTE v21[120]; // [rsp+E8h] [rbp-18h] BYREF
  int v22; // [rsp+160h] [rbp+60h]
  __int64 v23; // [rsp+180h] [rbp+80h] BYREF

  v17[0] = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v17[1] = L"CRegistryWriter::DestroyWriter";
  v17[2] = L"WRTREGRC";
  v18 = 576;
  v19 = 4;
  v20 = 255;
  v22 = 0x1000000;
  memset_0(v21, 0, sizeof(v21));
  v5 = 0;
  v10 = L"CRegistryWriter::DestroyWriter";
  v6 = L"base\\stor\\vss\\modules\\writers\\regwriter.cxx";
  v7 = L"WRTREGRC";
  v8 = 576;
  v9 = 4;
  TickCount = GetTickCount();
  v13 = 255;
  v4 = 0xFFFFFFFF00000000uLL;
  v16 = 0;
  v14 = 0;
  v15 = 0;
  v23 = 0;
  if ( (int)VssGetTracingContextPerThread(&v23) < 0 )
  {
    v1 = v16;
  }
  else
  {
    v0 = VssSetTracingContextPerThread(&v4);
    v1 = v16;
    if ( v0 >= 0 )
      v1 = v23;
    v16 = v1;
  }
  if ( v1 )
    v11 = *(_DWORD *)(v1 + 48) + 1;
  else
    v11 = 0;
  v2 = 160;
  if ( v13 != 255 )
    v2 = v13;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v4) )
    VssTraceMessage(v6, v7, v8, v11, v9, v10, L"ENTER", v2, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v17);
  if ( CRegistryWriter::sm_pWriter )
  {
    CRegistryWriter::Uninitialize(v3);
    if ( CRegistryWriter::sm_pWriter )
      (**(void (__fastcall ***)(CVssWriter *, __int64))CRegistryWriter::sm_pWriter)(CRegistryWriter::sm_pWriter, 1);
    CRegistryWriter::sm_pWriter = 0;
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v4);
}

```

## disassembly

```asm
0x140037fa0  mov     [rsp-8+arg_8], rbx
0x140037fa5  push    rbp
0x140037fa6  lea     rbp, [rsp-70h]
0x140037fab  sub     rsp, 170h
0x140037fb2  lea     rax, aBaseStorVssMod_31; "base\\stor\\vss\\modules\\writers\\regw"...
0x140037fb9  mov     [rbp+70h+var_B0], rax
0x140037fbd  lea     rax, aCregistrywrite_4; "CRegistryWriter::DestroyWriter"
0x140037fc4  mov     [rbp+70h+var_A8], rax
0x140037fc8  lea     rax, aWrtregrc; "WRTREGRC"
0x140037fcf  mov     [rbp+70h+var_A0], rax
0x140037fd3  mov     [rbp+70h+var_98], 240h
0x140037fda  mov     [rbp+70h+var_94], 4
0x140037fe1  mov     [rbp+70h+var_90], 0FFh
0x140037fe8  mov     [rbp+70h+var_10], 1000000h
0x140037fef  xor     edx, edx; Val
0x140037ff1  lea     r8d, [rdx+78h]; Size
0x140037ff5  lea     rcx, [rbp+70h+var_88]; void *
0x140037ff9  call    memset_0
0x140037ffe  mov     [rsp+170h+var_118], 0
0x140038006  mov     rax, [rbp+70h+var_A8]
0x14003800a  mov     [rsp+170h+var_F8], rax
0x14003800f  mov     rax, [rbp+70h+var_B0]
0x140038013  mov     [rsp+170h+var_110], rax
0x140038018  mov     rax, [rbp+70h+var_A0]
0x14003801c  mov     [rsp+170h+var_108], rax
0x140038021  mov     eax, [rbp+70h+var_98]
0x140038024  mov     [rsp+170h+var_100], eax
0x140038028  mov     eax, [rbp+70h+var_94]
0x14003802b  mov     [rsp+170h+var_FC], eax
0x14003802f  call    cs:__imp_GetTickCount
0x140038035  mov     [rbp+70h+var_EC], eax
0x140038038  mov     [rsp+170h+var_11C], 0FFFFFFFFh
0x140038040  mov     eax, [rbp+70h+var_90]
0x140038043  mov     [rbp+70h+var_E8], eax
0x140038046  mov     [rsp+170h+var_120], 0
0x14003804e  mov     [rbp+70h+var_C0], 0
0x140038056  xorps   xmm0, xmm0
0x140038059  movups  [rbp+70h+var_E0], xmm0
0x14003805d  movups  [rbp+70h+var_D0], xmm0
0x140038061  mov     [rbp+70h+arg_0], 0
0x14003806c  lea     rcx, [rbp+70h+arg_0]
0x140038073  call    cs:__imp_VssGetTracingContextPerThread
0x140038079  test    eax, eax
0x14003807b  js      short loc_14003809C
0x14003807d  lea     rcx, [rsp+170h+var_120]
0x140038082  call    cs:__imp_VssSetTracingContextPerThread
0x140038088  mov     rcx, [rbp+70h+var_C0]
0x14003808c  test    eax, eax
0x14003808e  cmovns  rcx, [rbp+70h+arg_0]
0x140038096  mov     [rbp+70h+var_C0], rcx
0x14003809a  jmp     short loc_1400380A0
0x14003809c  mov     rcx, [rbp+70h+var_C0]
0x1400380a0  test    rcx, rcx
0x1400380a3  jz      short loc_1400380AF
0x1400380a5  mov     eax, [rcx+30h]
0x1400380a8  inc     eax
0x1400380aa  mov     [rbp+70h+var_F0], eax
0x1400380ad  jmp     short loc_1400380B6
0x1400380af  mov     [rbp+70h+var_F0], 0
0x1400380b6  mov     ebx, 0A0h
0x1400380bb  cmp     [rbp+70h+var_E8], 0FFh
0x1400380c2  cmovnz  ebx, [rbp+70h+var_E8]
0x1400380c6  lea     rcx, [rsp+170h+var_120]; this
0x1400380cb  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x1400380d0  test    eax, eax
0x1400380d2  jz      short loc_140038118
0x1400380d4  mov     [rsp+170h+var_130], 0
0x1400380dd  mov     [rsp+170h+var_138], ebx
0x1400380e1  lea     rax, aEnter; "ENTER"
0x1400380e8  mov     [rsp+170h+var_140], rax
0x1400380ed  mov     rax, [rsp+170h+var_F8]
0x1400380f2  mov     [rsp+170h+var_148], rax
0x1400380f7  mov     eax, [rsp+170h+var_FC]
0x1400380fb  mov     [rsp+170h+var_150], eax
0x1400380ff  mov     r9d, [rbp+70h+var_F0]
0x140038103  mov     r8d, [rsp+170h+var_100]
0x140038108  mov     rdx, [rsp+170h+var_108]
0x14003810d  mov     rcx, [rsp+170h+var_110]
0x140038112  call    cs:__imp_VssTraceMessage
0x140038118  lea     rcx, [rbp+70h+var_B0]; this
0x14003811c  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140038121  nop
0x140038122  cmp     cs:?sm_pWriter@CRegistryWriter@@0PEAV1@EA, 0; CRegistryWriter * CRegistryWriter::sm_pWriter
0x14003812a  jz      short loc_140038158
0x14003812c  call    ?Uninitialize@CRegistryWriter@@AEAAJXZ; CRegistryWriter::Uninitialize(void)
0x140038131  mov     rcx, cs:?sm_pWriter@CRegistryWriter@@0PEAV1@EA; CRegistryWriter * CRegistryWriter::sm_pWriter
0x140038138  test    rcx, rcx
0x14003813b  jz      short loc_14003814D
0x14003813d  mov     rax, [rcx]
0x140038140  mov     edx, 1
0x140038145  mov     rax, [rax]
0x140038148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003814d  mov     cs:?sm_pWriter@CRegistryWriter@@0PEAV1@EA, 0; CRegistryWriter * CRegistryWriter::sm_pWriter
0x140038158  lea     rcx, [rsp+170h+var_120]; this
0x14003815d  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140038162  mov     rbx, [rsp+170h+arg_8]
0x14003816a  add     rsp, 170h
0x140038171  pop     rbp
0x140038172  retn
```
