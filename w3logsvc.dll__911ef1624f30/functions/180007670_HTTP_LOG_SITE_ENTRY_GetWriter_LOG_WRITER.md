# HTTP_LOG_SITE_ENTRY::GetWriter(LOG_WRITER * *)

- ea: `0x180007670`
- end: `0x18000773d`
- name: `?GetWriter@HTTP_LOG_SITE_ENTRY@@QEAAJPEAPEAVLOG_WRITER@@@Z`
- size: `205`
- prototype: `__int64 __fastcall(HTTP_LOG_SITE_ENTRY *__hidden this, struct LOG_WRITER **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000a57c`

## callees

- `0x180001008`
- `0x180002094`
- `0x1800057a0`
- `0x180007670`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007710`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800076d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007710`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000769b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000769b`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_SITE_ENTRY::GetWriter(HTTP_LOG_SITE_ENTRY *this, struct LOG_WRITER **a2)
{
  int v4; // esi
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  LOG_WRITER *v6; // rax
  LOG_WRITER *v7; // rbx

  v4 = 0;
  if ( *((_QWORD *)this + 10) )
    goto LABEL_13;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( *((_QWORD *)this + 10) )
  {
LABEL_12:
    LeaveCriticalSection(v5);
LABEL_13:
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 10) + 672LL));
    *a2 = (struct LOG_WRITER *)*((_QWORD *)this + 10);
    return (unsigned int)v4;
  }
  v6 = (LOG_WRITER *)operator new(0x2D8u);
  if ( v6 )
    v7 = LOG_WRITER::LOG_WRITER(v6);
  else
    v7 = 0;
  if ( !v7 )
  {
    v4 = -2147024882;
    goto LABEL_8;
  }
  v4 = LOG_WRITER::Initialize(v7, *((const struct HTTP_LOG_FILE_CONFIG_CONTEXT **)this + 11));
  if ( v4 >= 0 )
  {
    *((_QWORD *)this + 10) = v7;
    goto LABEL_12;
  }
LABEL_8:
  LeaveCriticalSection(v5);
  if ( v7 )
    (**(void (__fastcall ***)(LOG_WRITER *, __int64))v7)(v7, 1);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007670  mov     [rsp+arg_8], rbx
0x180007675  mov     [rsp+arg_10], rbp
0x18000767a  push    rsi
0x18000767b  push    rdi
0x18000767c  push    r14
0x18000767e  sub     rsp, 20h
0x180007682  mov     r14, rdx
0x180007685  mov     rdi, rcx
0x180007688  xor     esi, esi
0x18000768a  cmp     [rcx+50h], rsi
0x18000768e  jnz     loc_180007716
0x180007694  lea     rbp, [rcx+28h]
0x180007698  mov     rcx, rbp; lpCriticalSection
0x18000769b  call    cs:__imp_EnterCriticalSection
0x1800076a1  cmp     [rdi+50h], rsi
0x1800076a5  jnz     short loc_18000770D
0x1800076a7  mov     ecx, 2D8h; Size
0x1800076ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800076b1  mov     [rsp+38h+arg_0], rax
0x1800076b6  test    rax, rax
0x1800076b9  jz      short loc_1800076C8
0x1800076bb  mov     rcx, rax; this
0x1800076be  call    ??0LOG_WRITER@@QEAA@XZ; LOG_WRITER::LOG_WRITER(void)
0x1800076c3  mov     rbx, rax
0x1800076c6  jmp     short loc_1800076CA
0x1800076c8  xor     ebx, ebx
0x1800076ca  test    rbx, rbx
0x1800076cd  jnz     short loc_1800076F7
0x1800076cf  mov     esi, 8007000Eh
0x1800076d4  mov     rcx, rbp; lpCriticalSection
0x1800076d7  call    cs:__imp_LeaveCriticalSection
0x1800076dd  test    rbx, rbx
0x1800076e0  jz      short loc_180007728
0x1800076e2  mov     rax, [rbx]
0x1800076e5  mov     edx, 1
0x1800076ea  mov     rcx, rbx
0x1800076ed  mov     rax, [rax]
0x1800076f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f5  jmp     short loc_180007728
0x1800076f7  mov     rdx, [rdi+58h]; struct HTTP_LOG_FILE_CONFIG_CONTEXT *
0x1800076fb  mov     rcx, rbx; this
0x1800076fe  call    ?Initialize@LOG_WRITER@@QEAAJPEBVHTTP_LOG_FILE_CONFIG_CONTEXT@@@Z; LOG_WRITER::Initialize(HTTP_LOG_FILE_CONFIG_CONTEXT const *)
0x180007703  mov     esi, eax
0x180007705  test    eax, eax
0x180007707  js      short loc_1800076D4
0x180007709  mov     [rdi+50h], rbx
0x18000770d  mov     rcx, rbp; lpCriticalSection
0x180007710  call    cs:__imp_LeaveCriticalSection
0x180007716  mov     rax, [rdi+50h]
0x18000771a  lock inc dword ptr [rax+2A0h]
0x180007721  mov     rax, [rdi+50h]
0x180007725  mov     [r14], rax
0x180007728  mov     eax, esi
0x18000772a  mov     rbx, [rsp+38h+arg_8]
0x18000772f  mov     rbp, [rsp+38h+arg_10]
0x180007734  add     rsp, 20h
0x180007738  pop     r14
0x18000773a  pop     rdi
0x18000773b  pop     rsi
0x18000773c  retn
```
