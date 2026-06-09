# CTnMultiResCursor::CreateChild(CTnMultiResNode *)

- ea: `0x18000acb0`
- end: `0x18000ad12`
- name: `?CreateChild@CTnMultiResCursor@@QEAAPEAV1@PEAVCTnMultiResNode@@@Z`
- size: `98`
- prototype: `struct CTnMultiResCursor *__fastcall(CTnMultiResCursor *__hidden this, struct CTnMultiResNode *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a614`

## callees

- `0x180008da8`
- `0x18000acb0`

## pseudocode

```c
struct CTnMultiResCursor *__fastcall CTnMultiResCursor::CreateChild(
        CTnMultiResCursor *this,
        struct CTnMultiResNode *a2)
{
  CSpClassFactory *v4; // rcx
  struct CTnMultiResCursor *result; // rax
  struct CTnMultiResCursor *v6; // [rsp+30h] [rbp+8h] BYREF

  v4 = (CSpClassFactory *)*((_QWORD *)this + 1);
  if ( !v4 )
    return 0;
  v6 = 0;
  if ( (int)CSpClassFactory::CreateProduct<CTnMultiResCursor>(v4, &v6) < 0 )
    return 0;
  result = v6;
  if ( !v6 )
    return 0;
  *((_QWORD *)v6 + 4) = this;
  *((_DWORD *)result + 10) = *((_DWORD *)this + 10);
  if ( a2 )
  {
    *((_QWORD *)result + 3) = a2;
    *((_DWORD *)result + 10) += *((_DWORD *)a2 + 11);
  }
  return result;
}

```

## disassembly

```asm
0x18000acb0  mov     [rsp+arg_8], rbx
0x18000acb5  push    rdi
0x18000acb6  sub     rsp, 20h
0x18000acba  mov     rdi, rcx
0x18000acbd  mov     rbx, rdx
0x18000acc0  mov     rcx, [rcx+8]; this
0x18000acc4  test    rcx, rcx
0x18000acc7  jz      short loc_18000AD05
0x18000acc9  lea     rdx, [rsp+28h+arg_0]
0x18000acce  mov     [rsp+28h+arg_0], 0
0x18000acd7  call    ??$CreateProduct@VCTnMultiResCursor@@@CSpClassFactory@@QEAAJPEAPEAVCTnMultiResCursor@@@Z; CSpClassFactory::CreateProduct<CTnMultiResCursor>(CTnMultiResCursor * *)
0x18000acdc  test    eax, eax
0x18000acde  js      short loc_18000AD05
0x18000ace0  mov     rax, [rsp+28h+arg_0]
0x18000ace5  test    rax, rax
0x18000ace8  jz      short loc_18000AD05
0x18000acea  mov     [rax+20h], rdi
0x18000acee  mov     ecx, [rdi+28h]
0x18000acf1  mov     [rax+28h], ecx
0x18000acf4  test    rbx, rbx
0x18000acf7  jz      short loc_18000AD07
0x18000acf9  mov     [rax+18h], rbx
0x18000acfd  mov     ecx, [rbx+2Ch]
0x18000ad00  add     [rax+28h], ecx
0x18000ad03  jmp     short loc_18000AD07
0x18000ad05  xor     eax, eax
0x18000ad07  mov     rbx, [rsp+28h+arg_8]
0x18000ad0c  add     rsp, 20h
0x18000ad10  pop     rdi
0x18000ad11  retn
```
