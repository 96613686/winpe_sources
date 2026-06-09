# CleanupBackupUsers(ulong,_SD_BACKUP_USER_DATA *)

- ea: `0x18001813c`
- end: `0x1800181ed`
- name: `?CleanupBackupUsers@@YAJKPEAU_SD_BACKUP_USER_DATA@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(unsigned int, struct _SD_BACKUP_USER_DATA *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017f18`

## callees

- `0x18001586c`
- `0x180015974`
- `0x18001813c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001819c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018180`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001819c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800181b0`

## pseudocode

```c
__int64 __fastcall CleanupBackupUsers(unsigned int a1, struct _SD_BACKUP_USER_DATA *a2)
{
  __int64 i; // rbp
  __int64 v5; // rdi
  __int64 v6; // r14
  char *v7; // rsi
  unsigned int v8; // ebx
  _DWORD v10[30]; // [rsp+20h] [rbp-78h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)v10, "CleanupBackupUsers", 65, 1);
  for ( i = 0; (unsigned int)i < a1; *((_QWORD *)a2 + v5 + 4) = 0 )
  {
    v5 = 5 * i;
    CoTaskMemFree(*((LPVOID *)a2 + 5 * i));
    v6 = 0;
    v7 = (char *)a2 + 40 * i;
    if ( *((_DWORD *)v7 + 2) )
    {
      do
      {
        CoTaskMemFree(*(LPVOID *)(*((_QWORD *)v7 + 2) + 8 * v6));
        v6 = (unsigned int)(v6 + 1);
      }
      while ( (unsigned int)v6 < *((_DWORD *)a2 + 10 * i + 2) );
    }
    CoTaskMemFree(*((LPVOID *)v7 + 2));
    *(_OWORD *)((char *)a2 + 40 * i) = 0;
    i = (unsigned int)(i + 1);
    *(_OWORD *)((char *)a2 + 8 * v5 + 16) = 0;
  }
  v8 = v10[0];
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)v10);
  return v8;
}

```

## disassembly

```asm
0x18001813c  push    rbx
0x18001813e  push    rbp
0x18001813f  push    rsi
0x180018140  push    rdi
0x180018141  push    r14
0x180018143  push    r15
0x180018145  sub     rsp, 68h
0x180018149  mov     r9d, 1; unsigned __int16
0x18001814f  mov     rbx, rdx
0x180018152  mov     r15d, ecx
0x180018155  lea     rdx, aCleanupbackupu; "CleanupBackupUsers"
0x18001815c  lea     rcx, [rsp+98h+var_78]; this
0x180018161  lea     r8d, [r9+40h]; unsigned __int16
0x180018165  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001816a  xor     ebp, ebp
0x18001816c  test    r15d, r15d
0x18001816f  jz      short loc_1800181D0
0x180018171  lea     rdi, ds:0[rbp*4]
0x180018179  add     rdi, rbp
0x18001817c  mov     rcx, [rbx+rdi*8]; pv
0x180018180  call    cs:__imp_CoTaskMemFree
0x180018186  xor     r14d, r14d
0x180018189  lea     rsi, [rbx+rdi*8]
0x18001818d  cmp     [rbx+rdi*8+8], r14d
0x180018192  jbe     short loc_1800181AC
0x180018194  mov     rcx, [rsi+10h]
0x180018198  mov     rcx, [rcx+r14*8]; pv
0x18001819c  call    cs:__imp_CoTaskMemFree
0x1800181a2  inc     r14d
0x1800181a5  cmp     r14d, [rbx+rdi*8+8]
0x1800181aa  jb      short loc_180018194
0x1800181ac  mov     rcx, [rsi+10h]; pv
0x1800181b0  call    cs:__imp_CoTaskMemFree
0x1800181b6  xorps   xmm0, xmm0
0x1800181b9  xor     eax, eax
0x1800181bb  movups  xmmword ptr [rbx+rdi*8], xmm0
0x1800181bf  inc     ebp
0x1800181c1  movups  xmmword ptr [rbx+rdi*8+10h], xmm0
0x1800181c6  mov     [rbx+rdi*8+20h], rax
0x1800181cb  cmp     ebp, r15d
0x1800181ce  jb      short loc_180018171
0x1800181d0  mov     ebx, [rsp+98h+var_78]
0x1800181d4  lea     rcx, [rsp+98h+var_78]; this
0x1800181d9  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800181de  mov     eax, ebx
0x1800181e0  add     rsp, 68h
0x1800181e4  pop     r15
0x1800181e6  pop     r14
0x1800181e8  pop     rdi
0x1800181e9  pop     rsi
0x1800181ea  pop     rbp
0x1800181eb  pop     rbx
0x1800181ec  retn
```
