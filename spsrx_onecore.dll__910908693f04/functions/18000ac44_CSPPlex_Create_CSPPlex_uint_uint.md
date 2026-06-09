# CSPPlex::Create(CSPPlex * &,uint,uint)

- ea: `0x18000ac44`
- end: `0x18000aca8`
- name: `?Create@CSPPlex@@SAPEAU1@AEAPEAU1@II@Z`
- size: `100`
- prototype: `struct CSPPlex *__fastcall(struct CSPPlex **, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c50`
- `0x18000daf4`
- `0x18000db8c`
- `0x18000ec18`

## callees

- `0x180002ecc`
- `0x18000ac44`

## pseudocode

```c
struct CSPPlex *__fastcall CSPPlex::Create(struct CSPPlex **a1, unsigned int a2)
{
  struct CSPPlex *v3; // r8
  unsigned __int64 v5; // r9
  struct CSPPlex *v6; // rax

  v3 = 0;
  v5 = 24LL * a2;
  if ( v5 <= 0xFFFFFFFF && (int)v5 + 16 >= (unsigned int)v5 )
  {
    v6 = (struct CSPPlex *)operator new[]((unsigned int)(v5 + 16), (const struct std::nothrow_t *)&std::nothrow);
    v3 = v6;
    if ( v6 )
    {
      *((_DWORD *)v6 + 2) = a2;
      *((_DWORD *)v6 + 3) = 0;
      *(_QWORD *)v6 = *a1;
      *a1 = v6;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000ac44  mov     [rsp+arg_0], rbx
0x18000ac49  push    rdi
0x18000ac4a  sub     rsp, 20h
0x18000ac4e  mov     edi, edx
0x18000ac50  xor     r8d, r8d
0x18000ac53  mov     eax, 0FFFFFFFFh
0x18000ac58  mov     rbx, rcx
0x18000ac5b  lea     r9, [rdi+rdi*2]
0x18000ac5f  shl     r9, 3
0x18000ac63  cmp     r9, rax
0x18000ac66  ja      short loc_18000AC9A
0x18000ac68  lea     eax, [r9+10h]
0x18000ac6c  cmp     eax, r9d
0x18000ac6f  jb      short loc_18000AC9A
0x18000ac71  mov     ecx, eax; unsigned __int64
0x18000ac73  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac7a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000ac7f  mov     r8, rax
0x18000ac82  test    rax, rax
0x18000ac85  jz      short loc_18000AC9A
0x18000ac87  mov     [rax+8], edi
0x18000ac8a  mov     dword ptr [rax+0Ch], 0
0x18000ac91  mov     rcx, [rbx]
0x18000ac94  mov     [rax], rcx
0x18000ac97  mov     [rbx], rax
0x18000ac9a  mov     rbx, [rsp+28h+arg_0]
0x18000ac9f  mov     rax, r8
0x18000aca2  add     rsp, 20h
0x18000aca6  pop     rdi
0x18000aca7  retn
```
