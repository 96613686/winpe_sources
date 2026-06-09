# HashpInitHash(BCRYPT_HASH_CTXT *,ulong *)

- ea: `0x18001f550`
- end: `0x18001f5f6`
- name: `?HashpInitHash@@YAJPEAUBCRYPT_HASH_CTXT@@PEAK@Z`
- size: `166`
- prototype: `__int64 __fastcall(struct BCRYPT_HASH_CTXT *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800483ac`
- `0x180048418`

## callees

- `0x18001f550`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x18001f593`
- `bcrypt!BCryptCreateHash` at `0x18001f593`
- `bcrypt!BCryptGetProperty` at `0x18001f5c9`
- `bcrypt!BCryptGetProperty` at `0x18001f5c9`
- `bcrypt!BCryptDestroyHash` at `0x18001f5ee`
- `bcrypt!BCryptDestroyHash` at `0x18001f5ee`

## pseudocode

```c
NTSTATUS __fastcall HashpInitHash(struct BCRYPT_HASH_CTXT *a1, unsigned int *a2)
{
  BCRYPT_HANDLE *v2; // rdi
  NTSTATUS result; // eax
  unsigned int *v6; // r14
  NTSTATUS Property; // esi
  ULONG pcbResult; // [rsp+70h] [rbp+8h] BYREF

  v2 = (BCRYPT_HANDLE *)((char *)a1 + 8);
  pcbResult = 0;
  result = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)a1, (BCRYPT_HASH_HANDLE *)a1 + 1, (PUCHAR)a1 + 16, 0x200u, 0, 0, 0);
  if ( result >= 0 )
  {
    v6 = (unsigned int *)((char *)a1 + 528);
    Property = BCryptGetProperty(*v2, L"HashDigestLength", (PUCHAR)a1 + 528, 4u, &pcbResult, 0);
    if ( Property < 0 )
    {
      BCryptDestroyHash(*v2);
    }
    else if ( a2 )
    {
      *a2 = *v6;
    }
    return Property;
  }
  return result;
}

```

## disassembly

```asm
0x18001f550  mov     rax, rsp
0x18001f553  push    rbx
0x18001f554  push    rsi
0x18001f555  push    rdi
0x18001f556  push    r14
0x18001f558  sub     rsp, 48h
0x18001f55c  lea     rdi, [rcx+8]
0x18001f560  mov     dword ptr [rax-38h], 0
0x18001f567  mov     rbx, rdx
0x18001f56a  mov     dword ptr [rax-40h], 0
0x18001f571  mov     rsi, rcx
0x18001f574  mov     dword ptr [rax+8], 0
0x18001f57b  lea     r8, [rcx+10h]; pbHashObject
0x18001f57f  mov     qword ptr [rax-48h], 0
0x18001f587  mov     rcx, [rcx]; hAlgorithm
0x18001f58a  mov     rdx, rdi; phHash
0x18001f58d  mov     r9d, 200h; cbHashObject
0x18001f593  call    cs:__imp_BCryptCreateHash
0x18001f599  test    eax, eax
0x18001f59b  js      short loc_18001F5E1
0x18001f59d  mov     rcx, [rdi]; hObject
0x18001f5a0  lea     rax, [rsp+68h+arg_0]
0x18001f5a5  lea     r14, [rsi+210h]
0x18001f5ac  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18001f5b4  mov     r8, r14; pbOutput
0x18001f5b7  mov     [rsp+68h+pcbResult], rax; pcbResult
0x18001f5bc  mov     r9d, 4; cbOutput
0x18001f5c2  lea     rdx, pszProperty; "HashDigestLength"
0x18001f5c9  call    cs:__imp_BCryptGetProperty
0x18001f5cf  mov     esi, eax
0x18001f5d1  test    eax, eax
0x18001f5d3  js      short loc_18001F5EB
0x18001f5d5  test    rbx, rbx
0x18001f5d8  jz      short loc_18001F5DF
0x18001f5da  mov     eax, [r14]
0x18001f5dd  mov     [rbx], eax
0x18001f5df  mov     eax, esi
0x18001f5e1  add     rsp, 48h
0x18001f5e5  pop     r14
0x18001f5e7  pop     rdi
0x18001f5e8  pop     rsi
0x18001f5e9  pop     rbx
0x18001f5ea  retn
0x18001f5eb  mov     rcx, [rdi]; hHash
0x18001f5ee  call    cs:__imp_BCryptDestroyHash
0x18001f5f4  jmp     short loc_18001F5DF
```
