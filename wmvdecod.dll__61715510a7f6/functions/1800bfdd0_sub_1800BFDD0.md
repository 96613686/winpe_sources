# sub_1800BFDD0

- ea: `0x1800bfdd0`
- end: `0x1800bfe18`
- name: `sub_1800BFDD0`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800bf3b4`

## callees

- `0x1800bfdd0`

## import_xrefs

- `msdmo!MoDuplicateMediaType` at `0x1800bfe0c`
- `msdmo!MoDeleteMediaType` at `0x1800bfde9`
- `msdmo!MoDeleteMediaType` at `0x1800bfde9`

## pseudocode

```c
HRESULT __fastcall sub_1800BFDD0(__int64 a1, const DMO_MEDIA_TYPE *a2)
{
  DMO_MEDIA_TYPE **v2; // rbx
  DMO_MEDIA_TYPE *v4; // rcx

  v2 = (DMO_MEDIA_TYPE **)(a1 + 40);
  v4 = *(DMO_MEDIA_TYPE **)(a1 + 40);
  if ( v4 )
  {
    MoDeleteMediaType(v4);
    *v2 = 0;
  }
  return MoDuplicateMediaType(v2, a2);
}

```

## disassembly

```asm
0x1800bfdd0  mov     [rsp+arg_0], rbx
0x1800bfdd5  push    rdi
0x1800bfdd6  sub     rsp, 20h
0x1800bfdda  lea     rbx, [rcx+28h]
0x1800bfdde  mov     rdi, rdx
0x1800bfde1  mov     rcx, [rbx]; pmt
0x1800bfde4  test    rcx, rcx
0x1800bfde7  jz      short loc_1800BFDFC
0x1800bfde9  call    cs:MoDeleteMediaType
0x1800bfdf0  nop     dword ptr [rax+rax+00h]
0x1800bfdf5  mov     qword ptr [rbx], 0
0x1800bfdfc  mov     rdx, rdi
0x1800bfdff  mov     rcx, rbx
0x1800bfe02  mov     rbx, [rsp+28h+arg_0]
0x1800bfe07  add     rsp, 20h
0x1800bfe0b  pop     rdi
0x1800bfe0c  jmp     cs:MoDuplicateMediaType
```
