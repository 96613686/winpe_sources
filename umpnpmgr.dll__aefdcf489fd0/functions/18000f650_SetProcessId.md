# SetProcessId

- ea: `0x18000f650`
- end: `0x18000f6db`
- name: `SetProcessId`
- size: `139`
- prototype: `__int64 __fastcall(int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800056d0`

## callees

- `0x18000f650`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f6b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f6b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018e95`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000f67e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000f67e`

## pseudocode

```c
__int64 __fastcall SetProcessId(int a1, int a2)
{
  unsigned int v4; // edi
  PVOID *i; // rax

  v4 = 0;
  WaitForMultipleObjectsEx(2u, &qword_1800239B0, 0, 0xFFFFFFFF, 0);
  for ( i = (PVOID *)ServerInstallThreadIdList; i != &ServerInstallThreadIdList; i = (PVOID *)*i )
  {
    if ( *((_DWORD *)i + 4) == a1 )
    {
      *((_DWORD *)i + 5) = a2;
      v4 = 1;
      break;
    }
  }
  ReleaseMutex(qword_1800239B8);
  return v4;
}

```

## disassembly

```asm
0x18000f650  mov     [rsp+arg_0], rbx
0x18000f655  mov     [rsp+arg_8], rsi
0x18000f65a  push    rdi
0x18000f65b  sub     rsp, 30h
0x18000f65f  mov     ebx, edx
0x18000f661  mov     esi, ecx
0x18000f663  xor     edi, edi
0x18000f665  mov     [rsp+38h+bAlertable], edi; bAlertable
0x18000f669  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000f66f  xor     r8d, r8d; bWaitAll
0x18000f672  lea     rdx, qword_1800239B0; lpHandles
0x18000f679  mov     ecx, 2; nCount
0x18000f67e  call    cs:__imp_WaitForMultipleObjectsEx
0x18000f684  nop
0x18000f685  mov     rax, cs:ServerInstallThreadIdList
0x18000f68c  lea     rcx, ServerInstallThreadIdList
0x18000f693  cmp     rax, rcx
0x18000f696  jz      short loc_18000F6AC
0x18000f698  cmp     [rax+10h], esi
0x18000f69b  jnz     short loc_18000F6A7
0x18000f69d  mov     [rax+14h], ebx
0x18000f6a0  mov     edi, 1
0x18000f6a5  jmp     short loc_18000F6AC
0x18000f6a7  mov     rax, [rax]
0x18000f6aa  jmp     short loc_18000F693
0x18000f6ac  mov     rcx, cs:qword_1800239B8; hMutex
0x18000f6b3  call    cs:__imp_ReleaseMutex
0x18000f6b9  mov     eax, edi
0x18000f6bb  mov     rbx, [rsp+38h+arg_0]
0x18000f6c0  mov     rsi, [rsp+38h+arg_8]
0x18000f6c5  add     rsp, 30h
0x18000f6c9  pop     rdi
0x18000f6ca  retn
0x18000f6cb  mov     rbx, [rsp+38h+arg_0]
0x18000f6d0  mov     rsi, [rsp+38h+arg_8]
0x18000f6d5  add     rsp, 30h
0x18000f6d9  pop     rdi
0x18000f6da  retn
0x180018e80  push    rbp
0x180018e82  sub     rsp, 30h
0x180018e86  mov     rbp, rdx
0x180018e89  mov     rcx, cs:qword_1800239B8
0x180018e90  add     rsp, 30h
0x180018e94  pop     rbp
0x180018e95  jmp     cs:__imp_ReleaseMutex
```
