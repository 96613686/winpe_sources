# YCommitSpoolData(void *,ulong,ulong,ulong,uchar *,ulong,ulong *,Call_Route)

- ea: `0x1400380dc`
- end: `0x1400381e8`
- name: `?YCommitSpoolData@@YAKPEAXKKKPEAEKPEAKW4Call_Route@@@Z`
- size: `268`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140032750`
- `0x140032820`

## callees

- `0x140002a70`
- `0x140002ac0`
- `0x14001dc90`
- `0x1400380dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003811d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003815b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003819f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400381b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003811d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003815b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003819f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400381b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400381c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400381c3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003810f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003814d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003810f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003814d`

## pseudocode

```c
__int64 __fastcall YCommitSpoolData(
        void *a1,
        DWORD a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int *a7)
{
  HANDLE v11; // rdi
  DWORD LastError; // eax
  DWORD v13; // ebx
  int v14; // esi

  *a7 = 0;
  v11 = OpenProcess(0x40u, 0, a2);
  if ( !v11 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError != 5 )
    {
      if ( LastError )
        return v13;
    }
  }
  v14 = 0;
  if ( !(unsigned int)YImpersonateClient(1) )
  {
    v13 = GetLastError();
    goto LABEL_14;
  }
  if ( v11 || (v11 = OpenProcess(0x40u, 0, a2)) != 0 )
  {
    v13 = 0;
    goto LABEL_10;
  }
  v13 = GetLastError();
  if ( !v13 )
  {
LABEL_10:
    v14 = SplCommitSpoolData(a1, v11, a3, a4, a5, a6, a7);
    if ( !v14 )
      v13 = GetLastError();
  }
  YRevertToSelf(1);
LABEL_14:
  if ( v11 )
    CloseHandle(v11);
  if ( !v14 && !v13 )
    return 6;
  return v13;
}

```

## disassembly

```asm
0x1400380dc  push    rbx
0x1400380de  push    rbp
0x1400380df  push    rsi
0x1400380e0  push    rdi
0x1400380e1  push    r12
0x1400380e3  push    r13
0x1400380e5  push    r14
0x1400380e7  push    r15
0x1400380e9  sub     rsp, 48h
0x1400380ed  mov     r14, [rsp+88h+arg_30]
0x1400380f5  mov     r12d, r8d
0x1400380f8  mov     r8d, edx; dwProcessId
0x1400380fb  mov     ebp, edx
0x1400380fd  xor     edx, edx; bInheritHandle
0x1400380ff  mov     r13, rcx
0x140038102  mov     r15d, r9d
0x140038105  mov     dword ptr [r14], 0
0x14003810c  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14003810f  call    cs:__imp_OpenProcess
0x140038115  mov     rdi, rax
0x140038118  test    rax, rax
0x14003811b  jnz     short loc_140038132
0x14003811d  call    cs:__imp_GetLastError
0x140038123  mov     ebx, eax
0x140038125  cmp     eax, 5
0x140038128  jz      short loc_140038132
0x14003812a  test    eax, eax
0x14003812c  jnz     loc_1400381D5
0x140038132  xor     esi, esi
0x140038134  lea     ecx, [rsi+1]
0x140038137  call    ?YImpersonateClient@@YAHW4Call_Route@@@Z; YImpersonateClient(Call_Route)
0x14003813c  test    eax, eax
0x14003813e  jz      short loc_1400381B3
0x140038140  test    rdi, rdi
0x140038143  jnz     short loc_140038169
0x140038145  mov     r8d, ebp; dwProcessId
0x140038148  lea     ecx, [rsi+40h]; dwDesiredAccess
0x14003814b  xor     edx, edx; bInheritHandle
0x14003814d  call    cs:__imp_OpenProcess
0x140038153  mov     rdi, rax
0x140038156  test    rax, rax
0x140038159  jnz     short loc_140038169
0x14003815b  call    cs:__imp_GetLastError
0x140038161  mov     ebx, eax
0x140038163  test    eax, eax
0x140038165  jnz     short loc_1400381A7
0x140038167  jmp     short loc_14003816B
0x140038169  xor     ebx, ebx
0x14003816b  mov     eax, [rsp+88h+arg_28]
0x140038172  mov     r9d, r15d
0x140038175  mov     [rsp+88h+var_58], r14; __int64
0x14003817a  mov     r8d, r12d
0x14003817d  mov     [rsp+88h+var_60], eax; unsigned int
0x140038181  mov     rdx, rdi
0x140038184  mov     rax, [rsp+88h+arg_20]
0x14003818c  mov     rcx, r13; void *
0x14003818f  mov     [rsp+88h+var_68], rax; __int64
0x140038194  call    SplCommitSpoolData
0x140038199  mov     esi, eax
0x14003819b  test    eax, eax
0x14003819d  jnz     short loc_1400381A7
0x14003819f  call    cs:__imp_GetLastError
0x1400381a5  mov     ebx, eax
0x1400381a7  mov     ecx, 1
0x1400381ac  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x1400381b1  jmp     short loc_1400381BB
0x1400381b3  call    cs:__imp_GetLastError
0x1400381b9  mov     ebx, eax
0x1400381bb  test    rdi, rdi
0x1400381be  jz      short loc_1400381C9
0x1400381c0  mov     rcx, rdi; hObject
0x1400381c3  call    cs:__imp_CloseHandle
0x1400381c9  test    esi, esi
0x1400381cb  jnz     short loc_1400381D5
0x1400381cd  test    ebx, ebx
0x1400381cf  lea     eax, [rsi+6]
0x1400381d2  cmovz   ebx, eax
0x1400381d5  mov     eax, ebx
0x1400381d7  add     rsp, 48h
0x1400381db  pop     r15
0x1400381dd  pop     r14
0x1400381df  pop     r13
0x1400381e1  pop     r12
0x1400381e3  pop     rdi
0x1400381e4  pop     rsi
0x1400381e5  pop     rbp
0x1400381e6  pop     rbx
0x1400381e7  retn
```
