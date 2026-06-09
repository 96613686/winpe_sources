# BaseSrvSxsCreateProcess

- ea: `0x180001d70`
- end: `0x180001dfa`
- name: `BaseSrvSxsCreateProcess`
- size: `138`
- prototype: `__int64 __fastcall(HANDLE SourceProcessHandle, void *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180001450`
- `0x180001d70`
- `0x180001e00`

## pseudocode

```c
__int64 __fastcall BaseSrvSxsCreateProcess(HANDLE SourceProcessHandle, void *a2, __int64 a3)
{
  __int64 v4; // rbp
  __int64 *v7; // rdi
  __int64 result; // rax
  __int16 v9; // ax
  unsigned __int16 v10; // cx

  v4 = *(_QWORD *)(a3 + 576);
  if ( *(int *)(a3 + 96) < 0 )
  {
    v7 = (__int64 *)(a3 + 584);
    return InternalSxsCreateProcess(SourceProcessHandle, a2, a3, v4, *v7);
  }
  v9 = *(_WORD *)(a3 + 592);
  if ( v9 )
  {
    v10 = *(_WORD *)(a3 + 592);
    if ( v9 == 5 )
      v10 = 13;
  }
  else
  {
    v10 = 10;
  }
  v7 = (__int64 *)(a3 + 584);
  result = BaseSrvSxsDoSystemDefaultActivationContext(
             v10,
             (union _LARGE_INTEGER)a2,
             *(_QWORD *)(a3 + 576),
             *(_QWORD *)(a3 + 584));
  if ( (int)result >= 0 )
    return InternalSxsCreateProcess(SourceProcessHandle, a2, a3, v4, *v7);
  return result;
}

```

## disassembly

```asm
0x180001d70  push    rbx
0x180001d72  push    rbp
0x180001d73  push    rsi
0x180001d74  push    rdi
0x180001d75  push    r14
0x180001d77  sub     rsp, 30h
0x180001d7b  cmp     dword ptr [r8+60h], 0
0x180001d80  mov     rbx, r8
0x180001d83  mov     rbp, [r8+240h]
0x180001d8a  mov     rsi, rdx
0x180001d8d  mov     r14, rcx
0x180001d90  jge     short loc_180001DBE
0x180001d92  lea     rdi, [r8+248h]
0x180001d99  mov     rax, [rdi]
0x180001d9c  mov     r9, rbp
0x180001d9f  mov     r8, rbx
0x180001da2  mov     [rsp+58h+var_38], rax; __int64
0x180001da7  mov     rdx, rsi
0x180001daa  mov     rcx, r14; SourceProcessHandle
0x180001dad  call    InternalSxsCreateProcess
0x180001db2  add     rsp, 30h
0x180001db6  pop     r14
0x180001db8  pop     rdi
0x180001db9  pop     rsi
0x180001dba  pop     rbp
0x180001dbb  pop     rbx
0x180001dbc  retn
0x180001dbe  movzx   eax, word ptr [r8+250h]
0x180001dc6  test    ax, ax
0x180001dc9  jz      short loc_180001DEC
0x180001dcb  movzx   ecx, ax
0x180001dce  cmp     ax, 5
0x180001dd2  jz      short loc_180001DF3
0x180001dd4  lea     rdi, [r8+248h]
0x180001ddb  mov     r8, rbp
0x180001dde  mov     r9, [rdi]
0x180001de1  call    BaseSrvSxsDoSystemDefaultActivationContext
0x180001de6  test    eax, eax
0x180001de8  js      short loc_180001DB2
0x180001dea  jmp     short loc_180001D99
0x180001dec  mov     ecx, 0Ah
0x180001df1  jmp     short loc_180001DD4
0x180001df3  mov     ecx, 0Dh
0x180001df8  jmp     short loc_180001DD4
```
