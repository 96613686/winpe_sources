# UdfDeletePcb

- ea: `0x140030f44`
- end: `0x140030fe5`
- name: `UdfDeletePcb`
- size: `161`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003148`
- `0x14002c008`
- `0x14002d424`
- `0x140049f80`

## callees

- `0x140004340`
- `0x140030f44`

## import_xrefs

- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140030f5f`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140030f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030fc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140030fc8`

## pseudocode

```c
void __fastcall UdfDeletePcb(_QWORD *P)
{
  LARGE_MCB *v2; // rcx
  _DWORD *v3; // rbx

  v2 = (LARGE_MCB *)P[6];
  if ( v2 )
  {
    FsRtlUninitializeLargeMcb(v2);
    UdfFreePool(P + 6);
  }
  UdfFreePool(P + 7);
  v3 = P + 12;
  if ( P + 12 < &P[7 * *((unsigned __int16 *)P + 2) + 12] )
  {
    do
    {
      if ( *v3 == 1 )
      {
        UdfFreePool(v3 + 8);
        UdfFreePool(v3 + 10);
      }
      v3 += 14;
    }
    while ( v3 < (_DWORD *)&P[7 * *((unsigned __int16 *)P + 2) + 12] );
  }
  ExFreePoolWithTag(P, 0);
}

```

## disassembly

```asm
0x140030f44  mov     [rsp+arg_0], rbx
0x140030f49  mov     [rsp+arg_8], rsi
0x140030f4e  push    rdi
0x140030f4f  sub     rsp, 20h
0x140030f53  mov     rdi, rcx
0x140030f56  mov     rcx, [rcx+30h]; Mcb
0x140030f5a  test    rcx, rcx
0x140030f5d  jz      short loc_140030F74
0x140030f5f  call    cs:__imp_FsRtlUninitializeLargeMcb
0x140030f66  nop     dword ptr [rax+rax+00h]
0x140030f6b  lea     rcx, [rdi+30h]
0x140030f6f  call    UdfFreePool
0x140030f74  lea     rcx, [rdi+38h]
0x140030f78  call    UdfFreePool
0x140030f7d  movzx   eax, word ptr [rdi+4]
0x140030f81  lea     rbx, [rdi+60h]
0x140030f85  imul    rax, 38h ; '8'
0x140030f89  add     rax, 60h ; '`'
0x140030f8d  add     rax, rdi
0x140030f90  cmp     rbx, rax
0x140030f93  jnb     short loc_140030FC3
0x140030f95  mov     rsi, rbx
0x140030f98  cmp     dword ptr [rbx], 1
0x140030f9b  jnz     short loc_140030FAF
0x140030f9d  lea     rcx, [rbx+20h]
0x140030fa1  call    UdfFreePool
0x140030fa6  lea     rcx, [rbx+28h]
0x140030faa  call    UdfFreePool
0x140030faf  movzx   eax, word ptr [rdi+4]
0x140030fb3  add     rbx, 38h ; '8'
0x140030fb7  imul    rcx, rax, 38h ; '8'
0x140030fbb  add     rcx, rsi
0x140030fbe  cmp     rbx, rcx
0x140030fc1  jb      short loc_140030F98
0x140030fc3  xor     edx, edx; Tag
0x140030fc5  mov     rcx, rdi; P
0x140030fc8  call    cs:__imp_ExFreePoolWithTag
0x140030fcf  nop     dword ptr [rax+rax+00h]
0x140030fd4  mov     rbx, [rsp+28h+arg_0]
0x140030fd9  mov     rsi, [rsp+28h+arg_8]
0x140030fde  add     rsp, 20h
0x140030fe2  pop     rdi
0x140030fe3  retn
```
