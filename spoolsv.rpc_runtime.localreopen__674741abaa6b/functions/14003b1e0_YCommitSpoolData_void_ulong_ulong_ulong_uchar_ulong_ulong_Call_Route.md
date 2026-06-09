# YCommitSpoolData(void *,ulong,ulong,ulong,uchar *,ulong,ulong *,Call_Route)

- ea: `0x14003b1e0`
- end: `0x14003b31b`
- name: `?YCommitSpoolData@@YAKPEAXKKKPEAEKPEAKW4Call_Route@@@Z`
- size: `315`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400350c0`
- `0x1400351a0`

## callees

- `0x1400028e0`
- `0x140002940`
- `0x14001f6c0`
- `0x14003b1e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b2d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003b2d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b2ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003b2ef`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003b213`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003b261`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003b213`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14003b261`

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
0x14003b1e0  push    rbx
0x14003b1e2  push    rbp
0x14003b1e3  push    rsi
0x14003b1e4  push    rdi
0x14003b1e5  push    r12
0x14003b1e7  push    r13
0x14003b1e9  push    r14
0x14003b1eb  push    r15
0x14003b1ed  sub     rsp, 48h
0x14003b1f1  mov     r14, [rsp+88h+arg_30]
0x14003b1f9  mov     r12d, r8d
0x14003b1fc  mov     r8d, edx; dwProcessId
0x14003b1ff  mov     ebp, edx
0x14003b201  xor     edx, edx; bInheritHandle
0x14003b203  mov     r13, rcx
0x14003b206  mov     r15d, r9d
0x14003b209  mov     dword ptr [r14], 0
0x14003b210  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14003b213  call    cs:__imp_OpenProcess
0x14003b21a  nop     dword ptr [rax+rax+00h]
0x14003b21f  mov     rdi, rax
0x14003b222  test    rax, rax
0x14003b225  jnz     short loc_14003B242
0x14003b227  call    cs:__imp_GetLastError
0x14003b22e  nop     dword ptr [rax+rax+00h]
0x14003b233  mov     ebx, eax
0x14003b235  cmp     eax, 5
0x14003b238  jz      short loc_14003B242
0x14003b23a  test    eax, eax
0x14003b23c  jnz     loc_14003B307
0x14003b242  xor     esi, esi
0x14003b244  lea     ecx, [rsi+1]
0x14003b247  call    ?YImpersonateClient@@YAHW4Call_Route@@@Z; YImpersonateClient(Call_Route)
0x14003b24c  test    eax, eax
0x14003b24e  jz      loc_14003B2D9
0x14003b254  test    rdi, rdi
0x14003b257  jnz     short loc_14003B289
0x14003b259  mov     r8d, ebp; dwProcessId
0x14003b25c  lea     ecx, [rsi+40h]; dwDesiredAccess
0x14003b25f  xor     edx, edx; bInheritHandle
0x14003b261  call    cs:__imp_OpenProcess
0x14003b268  nop     dword ptr [rax+rax+00h]
0x14003b26d  mov     rdi, rax
0x14003b270  test    rax, rax
0x14003b273  jnz     short loc_14003B289
0x14003b275  call    cs:__imp_GetLastError
0x14003b27c  nop     dword ptr [rax+rax+00h]
0x14003b281  mov     ebx, eax
0x14003b283  test    eax, eax
0x14003b285  jnz     short loc_14003B2CD
0x14003b287  jmp     short loc_14003B28B
0x14003b289  xor     ebx, ebx
0x14003b28b  mov     eax, [rsp+88h+arg_28]
0x14003b292  mov     r9d, r15d
0x14003b295  mov     [rsp+88h+var_58], r14; __int64
0x14003b29a  mov     r8d, r12d
0x14003b29d  mov     [rsp+88h+var_60], eax; unsigned int
0x14003b2a1  mov     rdx, rdi
0x14003b2a4  mov     rax, [rsp+88h+arg_20]
0x14003b2ac  mov     rcx, r13; void *
0x14003b2af  mov     [rsp+88h+var_68], rax; __int64
0x14003b2b4  call    SplCommitSpoolData
0x14003b2b9  mov     esi, eax
0x14003b2bb  test    eax, eax
0x14003b2bd  jnz     short loc_14003B2CD
0x14003b2bf  call    cs:__imp_GetLastError
0x14003b2c6  nop     dword ptr [rax+rax+00h]
0x14003b2cb  mov     ebx, eax
0x14003b2cd  mov     ecx, 1
0x14003b2d2  call    ?YRevertToSelf@@YAJW4Call_Route@@@Z; YRevertToSelf(Call_Route)
0x14003b2d7  jmp     short loc_14003B2E7
0x14003b2d9  call    cs:__imp_GetLastError
0x14003b2e0  nop     dword ptr [rax+rax+00h]
0x14003b2e5  mov     ebx, eax
0x14003b2e7  test    rdi, rdi
0x14003b2ea  jz      short loc_14003B2FB
0x14003b2ec  mov     rcx, rdi; hObject
0x14003b2ef  call    cs:__imp_CloseHandle
0x14003b2f6  nop     dword ptr [rax+rax+00h]
0x14003b2fb  test    esi, esi
0x14003b2fd  jnz     short loc_14003B307
0x14003b2ff  test    ebx, ebx
0x14003b301  lea     eax, [rsi+6]
0x14003b304  cmovz   ebx, eax
0x14003b307  mov     eax, ebx
0x14003b309  add     rsp, 48h
0x14003b30d  pop     r15
0x14003b30f  pop     r14
0x14003b311  pop     r13
0x14003b313  pop     r12
0x14003b315  pop     rdi
0x14003b316  pop     rsi
0x14003b317  pop     rbp
0x14003b318  pop     rbx
0x14003b319  retn
```
