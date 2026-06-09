# UdfCreatePcb

- ea: `0x14002db80`
- end: `0x14002dc09`
- name: `UdfCreatePcb`
- size: `137`
- prototype: `char *__fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002d424`

## callees

- `0x14001c080`
- `0x14002db80`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dbaa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14002dbaa`

## pseudocode

```c
char *__fastcall UdfCreatePcb(int a1)
{
  __int16 v1; // di
  unsigned int v2; // ebp
  char *PoolWithTag; // rax
  char *v4; // rbx
  char *result; // rax

  v1 = a1;
  if ( (unsigned int)(a1 - 1) > 0xFFFD )
    return 0;
  v2 = 56 * a1 + 96;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)1041, v2, 0x70666455u);
  v4 = PoolWithTag;
  if ( !ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      memset(PoolWithTag, 0, v2);
  }
  *(_WORD *)v4 = 2362;
  *((_WORD *)v4 + 44) = -1;
  result = v4;
  *((_WORD *)v4 + 1) = v2;
  *((_WORD *)v4 + 2) = v1;
  *(_DWORD *)(v4 + 90) = -1;
  *((_DWORD *)v4 + 21) = -1;
  return result;
}

```

## disassembly

```asm
0x14002db80  push    rbx
0x14002db82  push    rbp
0x14002db83  push    rsi
0x14002db84  push    rdi
0x14002db85  sub     rsp, 28h
0x14002db89  lea     eax, [rcx-1]
0x14002db8c  mov     edi, ecx
0x14002db8e  cmp     eax, 0FFFDh
0x14002db93  ja      short loc_14002DBFD
0x14002db95  imul    ebp, edi, 38h ; '8'
0x14002db98  mov     r8d, 70666455h; Tag
0x14002db9e  mov     ecx, 411h; PoolType
0x14002dba3  add     ebp, 60h ; '`'
0x14002dba6  mov     edx, ebp; NumberOfBytes
0x14002dba8  mov     esi, ebp
0x14002dbaa  call    cs:__imp_ExAllocatePoolWithTag
0x14002dbb1  nop     dword ptr [rax+rax+00h]
0x14002dbb6  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14002dbbd  mov     rbx, rax
0x14002dbc0  jnz     short loc_14002DBD4
0x14002dbc2  test    rax, rax
0x14002dbc5  jz      short loc_14002DBD4
0x14002dbc7  mov     r8d, esi; Size
0x14002dbca  xor     edx, edx; Val
0x14002dbcc  mov     rcx, rax; void *
0x14002dbcf  call    memset
0x14002dbd4  mov     eax, 0FFFFh
0x14002dbd9  mov     word ptr [rbx], 93Ah
0x14002dbde  mov     [rbx+58h], ax
0x14002dbe2  mov     rax, rbx
0x14002dbe5  mov     [rbx+2], bp
0x14002dbe9  mov     [rbx+4], di
0x14002dbed  mov     dword ptr [rbx+5Ah], 0FFFFFFFFh
0x14002dbf4  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x14002dbfb  jmp     short loc_14002DBFF
0x14002dbfd  xor     eax, eax
0x14002dbff  add     rsp, 28h
0x14002dc03  pop     rdi
0x14002dc04  pop     rsi
0x14002dc05  pop     rbp
0x14002dc06  pop     rbx
0x14002dc07  retn
```
