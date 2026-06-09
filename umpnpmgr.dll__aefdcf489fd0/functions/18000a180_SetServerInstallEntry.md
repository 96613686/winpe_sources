# SetServerInstallEntry

- ea: `0x18000a180`
- end: `0x18000a1fd`
- name: `SetServerInstallEntry`
- size: `125`
- prototype: `__int64 __fastcall(int, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180009d70`

## callees

- `0x18000a180`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000a1e5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018ca5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a1af`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000a1af`

## pseudocode

```c
__int64 __fastcall SetServerInstallEntry(int a1, void *a2)
{
  unsigned int v4; // edi
  PVOID *i; // rax

  v4 = 0;
  WaitForMultipleObjectsEx(2u, &qword_1800239B0, 0, 0xFFFFFFFF, 0);
  for ( i = (PVOID *)ServerInstallThreadIdList; i != &ServerInstallThreadIdList; i = (PVOID *)*i )
  {
    if ( *((_DWORD *)i + 4) == a1 )
    {
      i[3] = a2;
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
0x18000a180  mov     [rsp+arg_0], rbx
0x18000a185  mov     [rsp+arg_8], rsi
0x18000a18a  push    rdi
0x18000a18b  sub     rsp, 30h
0x18000a18f  mov     rsi, rdx
0x18000a192  mov     ebx, ecx
0x18000a194  xor     edi, edi
0x18000a196  mov     [rsp+38h+bAlertable], edi; bAlertable
0x18000a19a  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x18000a1a0  xor     r8d, r8d; bWaitAll
0x18000a1a3  lea     rdx, qword_1800239B0; lpHandles
0x18000a1aa  mov     ecx, 2; nCount
0x18000a1af  call    cs:__imp_WaitForMultipleObjectsEx
0x18000a1b5  nop
0x18000a1b6  mov     rax, cs:ServerInstallThreadIdList
0x18000a1bd  lea     rcx, ServerInstallThreadIdList
0x18000a1c4  cmp     rax, rcx
0x18000a1c7  jz      short loc_18000A1DE
0x18000a1c9  cmp     [rax+10h], ebx
0x18000a1cc  jnz     short loc_18000A1D9
0x18000a1ce  mov     [rax+18h], rsi
0x18000a1d2  mov     edi, 1
0x18000a1d7  jmp     short loc_18000A1DE
0x18000a1d9  mov     rax, [rax]
0x18000a1dc  jmp     short loc_18000A1C4
0x18000a1de  mov     rcx, cs:qword_1800239B8; hMutex
0x18000a1e5  call    cs:__imp_ReleaseMutex
0x18000a1eb  mov     eax, edi
0x18000a1ed  mov     rbx, [rsp+38h+arg_0]
0x18000a1f2  mov     rsi, [rsp+38h+arg_8]
0x18000a1f7  add     rsp, 30h
0x18000a1fb  pop     rdi
0x18000a1fc  retn
0x180018c90  push    rbp
0x180018c92  sub     rsp, 30h
0x180018c96  mov     rbp, rdx
0x180018c99  mov     rcx, cs:qword_1800239B8
0x180018ca0  add     rsp, 30h
0x180018ca4  pop     rbp
0x180018ca5  jmp     cs:__imp_ReleaseMutex
```
