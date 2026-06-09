# SampDuplicateUnicodeString(_UNICODE_STRING *)

- ea: `0x180015e18`
- end: `0x180015ee1`
- name: `?SampDuplicateUnicodeString@@YAPEAGPEAU_UNICODE_STRING@@@Z`
- size: `201`
- prototype: `unsigned __int16 *__fastcall(struct _UNICODE_STRING *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c50`
- `0x180004dd0`
- `0x18000d020`
- `0x18000d330`
- `0x18000d630`
- `0x18000d930`
- `0x18000dde0`
- `0x18000eca0`

## callees

- `0x180006ec2`
- `0x180015e18`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ecd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ecd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015e52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015e52`

## pseudocode

```c
unsigned __int16 *__fastcall SampDuplicateUnicodeString(struct _UNICODE_STRING *a1)
{
  _WORD *v2; // rbp
  unsigned int Length; // eax
  _WORD *v4; // rdi
  unsigned int v5; // ecx
  unsigned __int64 v6; // rbx
  _WORD *v7; // rax
  PWSTR Buffer; // rcx
  unsigned __int64 v9; // rbx
  _WORD *v10; // rax
  unsigned __int64 v11; // rdx
  _WORD *v12; // rcx

  v2 = 0;
  if ( a1 )
  {
    Length = a1->Length;
    v4 = 0;
    v5 = Length + 2;
    if ( Length + 2 < Length )
      goto LABEL_18;
  }
  else
  {
    v5 = 2;
  }
  v6 = v5;
  v7 = LocalAlloc(0x40u, v5);
  v4 = v7;
  if ( v7 )
  {
    memset_0(v7, 0, (unsigned int)v6);
    if ( !a1 )
      goto LABEL_17;
    if ( !a1->Length )
      goto LABEL_17;
    Buffer = a1->Buffer;
    if ( !Buffer )
      goto LABEL_17;
    v9 = v6 >> 1;
    if ( v9 )
    {
      v10 = v4;
      v11 = (unsigned __int64)a1->Length >> 1;
      do
      {
        if ( !v11 )
          break;
        if ( !*Buffer )
          break;
        *v10++ = *Buffer++;
        --v11;
        --v9;
      }
      while ( v9 );
      v12 = v10 - 1;
      if ( v9 )
        v12 = v10;
      *v12 = 0;
      if ( v9 )
      {
LABEL_17:
        v2 = v4;
        v4 = 0;
      }
    }
  }
LABEL_18:
  LocalFree(v4);
  return v2;
}

```

## disassembly

```asm
0x180015e18  push    rbx
0x180015e1a  push    rbp
0x180015e1b  push    rsi
0x180015e1c  push    rdi
0x180015e1d  push    r14
0x180015e1f  sub     rsp, 20h
0x180015e23  xor     r14d, r14d
0x180015e26  mov     rsi, rcx
0x180015e29  mov     ebp, r14d
0x180015e2c  test    rcx, rcx
0x180015e2f  jz      short loc_180015E44
0x180015e31  movzx   eax, word ptr [rcx]
0x180015e34  mov     edi, r14d
0x180015e37  lea     ecx, [rax+2]
0x180015e3a  cmp     ecx, eax
0x180015e3c  jb      loc_180015ECA
0x180015e42  jmp     short loc_180015E49
0x180015e44  mov     ecx, 2
0x180015e49  mov     ebx, ecx
0x180015e4b  mov     edx, ecx; uBytes
0x180015e4d  mov     ecx, 40h ; '@'; uFlags
0x180015e52  call    cs:__imp_LocalAlloc
0x180015e58  mov     rdi, rax
0x180015e5b  test    rax, rax
0x180015e5e  jz      short loc_180015ECA
0x180015e60  mov     r8d, ebx; Size
0x180015e63  xor     edx, edx; Val
0x180015e65  mov     rcx, rax; void *
0x180015e68  call    memset_0
0x180015e6d  test    rsi, rsi
0x180015e70  jz      short loc_180015EC4
0x180015e72  cmp     [rsi], r14w
0x180015e76  jbe     short loc_180015EC4
0x180015e78  mov     rcx, [rsi+8]
0x180015e7c  test    rcx, rcx
0x180015e7f  jz      short loc_180015EC4
0x180015e81  shr     rbx, 1
0x180015e84  jz      short loc_180015ECA
0x180015e86  movzx   edx, word ptr [rsi]
0x180015e89  mov     rax, rdi
0x180015e8c  shr     rdx, 1
0x180015e8f  test    rdx, rdx
0x180015e92  jz      short loc_180015EB3
0x180015e94  movzx   r8d, word ptr [rcx]
0x180015e98  test    r8w, r8w
0x180015e9c  jz      short loc_180015EB3
0x180015e9e  mov     [rax], r8w
0x180015ea2  add     rcx, 2
0x180015ea6  add     rax, 2
0x180015eaa  dec     rdx
0x180015ead  sub     rbx, 1
0x180015eb1  jnz     short loc_180015E8F
0x180015eb3  test    rbx, rbx
0x180015eb6  lea     rcx, [rax-2]
0x180015eba  cmovnz  rcx, rax
0x180015ebe  mov     [rcx], r14w
0x180015ec2  jz      short loc_180015ECA
0x180015ec4  mov     rbp, rdi
0x180015ec7  mov     rdi, r14
0x180015eca  mov     rcx, rdi; hMem
0x180015ecd  call    cs:__imp_LocalFree
0x180015ed3  mov     rax, rbp
0x180015ed6  add     rsp, 20h
0x180015eda  pop     r14
0x180015edc  pop     rdi
0x180015edd  pop     rsi
0x180015ede  pop     rbp
0x180015edf  pop     rbx
0x180015ee0  retn
```
