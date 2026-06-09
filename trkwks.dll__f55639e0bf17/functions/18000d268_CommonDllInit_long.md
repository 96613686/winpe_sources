# CommonDllInit(long *)

- ea: `0x18000d268`
- end: `0x18000d2f0`
- name: `?CommonDllInit@@YAXPEAJ@Z`
- size: `136`
- prototype: `void __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001d4c`

## callees

- `0x18000d038`
- `0x18000d268`
- `0x18000d2f8`
- `0x18000dae8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d2a9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000d2a9`

## pseudocode

```c
void __fastcall CommonDllInit(int *a1)
{
  char *v1; // rax
  CActiveThreadList *v2; // rbx
  _OWORD *v3; // rax

  if ( !(unsigned int)BeginSingleInstanceTask(&g_ctrkwks) )
    TrkRaiseWin32Error(1056);
  g_fRestorePrivilegeEnabled = 0;
  v1 = (char *)operator new(0x38u);
  v2 = (CActiveThreadList *)v1;
  if ( v1 )
  {
    InitializeCriticalSection((LPCRITICAL_SECTION)(v1 + 16));
    *(_QWORD *)v2 = 0;
    v3 = operator new(0x28u);
    *((_QWORD *)v2 + 1) = v3;
    if ( v3 )
    {
      *(_DWORD *)v2 = 10;
      *v3 = 0;
      v3[1] = 0;
      *((_QWORD *)v3 + 4) = 0;
    }
  }
  else
  {
    v2 = 0;
  }
  g_pActiveThreadList = v2;
}

```

## disassembly

```asm
0x18000d268  push    rbx
0x18000d26a  sub     rsp, 20h
0x18000d26e  lea     rcx, ?g_ctrkwks@@3JA; int *
0x18000d275  call    ?BeginSingleInstanceTask@@YAHPEAJ@Z; BeginSingleInstanceTask(long *)
0x18000d27a  test    eax, eax
0x18000d27c  jnz     short loc_18000D289
0x18000d27e  mov     ecx, 420h; int
0x18000d283  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x18000d289  mov     ecx, 38h ; '8'; Size
0x18000d28e  mov     cs:?g_fRestorePrivilegeEnabled@@3HA, 0; int g_fRestorePrivilegeEnabled
0x18000d298  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d29d  mov     rbx, rax
0x18000d2a0  test    rax, rax
0x18000d2a3  jz      short loc_18000D2E1
0x18000d2a5  lea     rcx, [rax+10h]; lpCriticalSection
0x18000d2a9  call    cs:__imp_InitializeCriticalSection
0x18000d2af  mov     ecx, 28h ; '('; Size
0x18000d2b4  mov     qword ptr [rbx], 0
0x18000d2bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d2c0  mov     [rbx+8], rax
0x18000d2c4  test    rax, rax
0x18000d2c7  jz      short loc_18000D2E3
0x18000d2c9  mov     dword ptr [rbx], 0Ah
0x18000d2cf  xorps   xmm0, xmm0
0x18000d2d2  movups  xmmword ptr [rax], xmm0
0x18000d2d5  xor     ecx, ecx
0x18000d2d7  movups  xmmword ptr [rax+10h], xmm0
0x18000d2db  mov     [rax+20h], rcx
0x18000d2df  jmp     short loc_18000D2E3
0x18000d2e1  xor     ebx, ebx
0x18000d2e3  mov     cs:g_pActiveThreadList, rbx
0x18000d2ea  add     rsp, 20h
0x18000d2ee  pop     rbx
0x18000d2ef  retn
```
