# _AcquireInitMutex

- ea: `0x18001086c`
- end: `0x180010916`
- name: `_AcquireInitMutex`
- size: `170`
- prototype: `__int64 __fastcall(signed __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fccc`
- `0x18001621c`
- `0x18001632c`

## callees

- `0x18001086c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800108df`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800108df`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800108a7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800108a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800108ee`

## pseudocode

```c
__int64 __fastcall AcquireInitMutex(signed __int64 a1)
{
  __int64 result; // rax
  signed __int64 v3; // rcx
  DWORD v4; // edi

  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
  if ( !_InterlockedCompareExchange64(&qword_180023830, a1, 0) )
    return 1;
  result = (__int64)CreateEventW(0, 0, 0, 0);
  *(_QWORD *)a1 = result;
  if ( result )
  {
    do
    {
      v3 = qword_180023830;
      *(_QWORD *)(a1 + 8) = qword_180023830;
    }
    while ( v3 != _InterlockedCompareExchange64(&qword_180023830, a1, v3) );
    if ( v3 )
      v4 = WaitForSingleObjectEx(*(HANDLE *)a1, 0xFFFFFFFF, 0);
    else
      v4 = 0;
    CloseHandle(*(HANDLE *)a1);
    *(_QWORD *)a1 = 0;
    return v4 == 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001086c  mov     [rsp+arg_0], rbx
0x180010871  push    rdi
0x180010872  sub     rsp, 20h
0x180010876  mov     rbx, rcx
0x180010879  mov     qword ptr [rcx+10h], 0
0x180010881  mov     qword ptr [rcx+8], 0
0x180010889  xor     eax, eax
0x18001088b  mov     qword ptr [rcx], 0
0x180010892  lock cmpxchg cs:qword_180023830, rbx
0x18001089b  jz      short loc_180010906
0x18001089d  xor     r9d, r9d; lpName
0x1800108a0  xor     r8d, r8d; bInitialState
0x1800108a3  xor     edx, edx; bManualReset
0x1800108a5  xor     ecx, ecx; lpEventAttributes
0x1800108a7  call    cs:__imp_CreateEventW
0x1800108ad  mov     [rbx], rax
0x1800108b0  test    rax, rax
0x1800108b3  jz      short loc_180010904
0x1800108b5  mov     rcx, cs:qword_180023830
0x1800108bc  mov     [rbx+8], rcx
0x1800108c0  mov     rax, rcx
0x1800108c3  lock cmpxchg cs:qword_180023830, rbx
0x1800108cc  cmp     rcx, rax
0x1800108cf  jnz     short loc_1800108B5
0x1800108d1  test    rcx, rcx
0x1800108d4  jz      short loc_1800108E9
0x1800108d6  mov     rcx, [rbx]; hHandle
0x1800108d9  xor     r8d, r8d; bAlertable
0x1800108dc  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800108df  call    cs:__imp_WaitForSingleObjectEx
0x1800108e5  mov     edi, eax
0x1800108e7  jmp     short loc_1800108EB
0x1800108e9  xor     edi, edi
0x1800108eb  mov     rcx, [rbx]; hObject
0x1800108ee  call    cs:__imp_CloseHandle
0x1800108f4  xor     eax, eax
0x1800108f6  mov     qword ptr [rbx], 0
0x1800108fd  test    edi, edi
0x1800108ff  setz    al
0x180010902  jmp     short loc_18001090B
0x180010904  jmp     short loc_18001090B
0x180010906  mov     eax, 1
0x18001090b  mov     rbx, [rsp+28h+arg_0]
0x180010910  add     rsp, 20h
0x180010914  pop     rdi
0x180010915  retn
```
