# SHWriteDataBlockList

- ea: `0x180009550`
- end: `0x1800095e4`
- name: `SHWriteDataBlockList`
- size: `148`
- prototype: `__int64 __fastcall(IStream *pstm)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180009550`
- `0x180012550`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18000958a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800095d3`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x18000958a`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800095d3`

## pseudocode

```c
int __fastcall SHWriteDataBlockList(IStream *pstm, unsigned int *a2)
{
  unsigned int *v2; // rbx
  int result; // eax
  _DWORD *v5; // rdx
  int pv; // [rsp+20h] [rbp-18h] BYREF

  v2 = a2;
  if ( a2 && *a2 )
  {
    while ( 1 )
    {
      v5 = v2 + 2;
      if ( v2[1] != -1 )
        v5 = v2;
      if ( *v5 > 8u )
      {
        result = IStream_Write(pstm, v5, *v5);
        if ( result < 0 )
          break;
      }
      v2 = (unsigned int *)((char *)v2 + *v2);
      if ( !*v2 )
        goto LABEL_2;
    }
  }
  else
  {
LABEL_2:
    pv = 0;
    return IStream_Write(pstm, &pv, 4u);
  }
  return result;
}

```

## disassembly

```asm
0x180009550  mov     [rsp+arg_10], rbx
0x180009555  push    rdi
0x180009556  sub     rsp, 30h
0x18000955a  mov     rax, cs:__security_cookie
0x180009561  xor     rax, rsp
0x180009564  mov     [rsp+38h+var_10], rax
0x180009569  mov     rbx, rdx
0x18000956c  mov     rdi, rcx
0x18000956f  test    rdx, rdx
0x180009572  jnz     short loc_1800095A8
0x180009574  mov     r8d, 4; cb
0x18000957a  mov     [rsp+38h+pv], 0
0x180009582  lea     rdx, [rsp+38h+pv]; pv
0x180009587  mov     rcx, rdi; pstm
0x18000958a  call    cs:__imp_IStream_Write
0x180009590  mov     rcx, [rsp+38h+var_10]
0x180009595  xor     rcx, rsp; StackCookie
0x180009598  call    __security_check_cookie
0x18000959d  mov     rbx, [rsp+38h+arg_10]
0x1800095a2  add     rsp, 30h
0x1800095a6  pop     rdi
0x1800095a7  retn
0x1800095a8  xor     eax, eax
0x1800095aa  cmp     [rdx], eax
0x1800095ac  jz      short loc_180009574
0x1800095ae  cmp     dword ptr [rbx+4], 0FFFFFFFFh
0x1800095b2  lea     rdx, [rbx+8]; pv
0x1800095b6  jnz     short loc_1800095DF
0x1800095b8  cmp     dword ptr [rdx], 8
0x1800095bb  ja      short loc_1800095CD
0x1800095bd  mov     edx, [rbx]
0x1800095bf  add     rbx, rdx
0x1800095c2  cmp     dword ptr [rbx], 0
0x1800095c5  jnz     short loc_1800095AE
0x1800095c7  test    eax, eax
0x1800095c9  jns     short loc_180009574
0x1800095cb  jmp     short loc_180009590
0x1800095cd  mov     r8d, [rdx]; cb
0x1800095d0  mov     rcx, rdi; pstm
0x1800095d3  call    cs:__imp_IStream_Write
0x1800095d9  test    eax, eax
0x1800095db  js      short loc_180009590
0x1800095dd  jmp     short loc_1800095BD
0x1800095df  mov     rdx, rbx
0x1800095e2  jmp     short loc_1800095B8
```
