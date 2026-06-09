# CAccessControlList::Add(void *,ulong,uchar)

- ea: `0x180004980`
- end: `0x180004a16`
- name: `?Add@CAccessControlList@@QEAAJPEAXKE@Z`
- size: `150`
- prototype: `__int64 __fastcall(CAccessControlList *this, void *, int, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004744`

## callees

- `0x180004980`
- `0x180004a1c`
- `0x18000f9c2`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000499f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000499f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a0c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004a0c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800049ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800049ae`

## pseudocode

```c
__int64 __fastcall CAccessControlList::Add(CAccessControlList *this, void *a2, int a3, char a4)
{
  DWORD LengthSid; // esi
  char *v9; // rax
  void *v10; // rbx
  __int64 result; // rax
  unsigned int v12; // edi
  void *v13; // [rsp+20h] [rbp-48h] BYREF

  LengthSid = GetLengthSid(a2);
  v9 = (char *)LocalAlloc(0, LengthSid + 8);
  v10 = v9;
  if ( !v9 )
    return 3221225495LL;
  *v9 = 0;
  v9[1] = a4;
  *((_WORD *)v9 + 1) = LengthSid + 8;
  *((_DWORD *)v9 + 1) = a3;
  memcpy_0(v9 + 8, a2, LengthSid);
  v13 = v10;
  result = CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add((unsigned int *)this + 2, &v13);
  v12 = result;
  if ( (int)result < 0 )
  {
    LocalFree(v10);
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180004980  push    rbx
0x180004982  push    rbp
0x180004983  push    rsi
0x180004984  push    rdi
0x180004985  push    r13
0x180004987  push    r14
0x180004989  push    r15
0x18000498b  sub     rsp, 30h
0x18000498f  mov     r13, rcx
0x180004992  movzx   r14d, r9b
0x180004996  mov     rcx, rdx; pSid
0x180004999  mov     r15d, r8d
0x18000499c  mov     rdi, rdx
0x18000499f  call    cs:__imp_GetLengthSid
0x1800049a5  mov     esi, eax
0x1800049a7  xor     ecx, ecx; uFlags
0x1800049a9  lea     ebp, [rsi+8]
0x1800049ac  mov     edx, ebp; uBytes
0x1800049ae  call    cs:__imp_LocalAlloc
0x1800049b4  mov     rbx, rax
0x1800049b7  test    rax, rax
0x1800049ba  jz      short loc_180004A02
0x1800049bc  mov     r8d, esi; Size
0x1800049bf  mov     byte ptr [rax], 0
0x1800049c2  lea     rcx, [rax+8]; void *
0x1800049c6  mov     [rax+1], r14b
0x1800049ca  mov     rdx, rdi; Src
0x1800049cd  mov     [rax+2], bp
0x1800049d1  mov     [rax+4], r15d
0x1800049d5  call    memcpy_0
0x1800049da  lea     rcx, [r13+8]
0x1800049de  mov     [rsp+68h+var_48], rbx
0x1800049e3  lea     rdx, [rsp+68h+var_48]
0x1800049e8  call    ?Add@?$CDynamicArray@PEAU_ACCESS_ALLOWED_ACE@@@@QEAAJAEBQEAU_ACCESS_ALLOWED_ACE@@@Z; CDynamicArray<_ACCESS_ALLOWED_ACE *>::Add(_ACCESS_ALLOWED_ACE * const &)
0x1800049ed  mov     edi, eax
0x1800049ef  test    eax, eax
0x1800049f1  js      short loc_180004A09
0x1800049f3  add     rsp, 30h
0x1800049f7  pop     r15
0x1800049f9  pop     r14
0x1800049fb  pop     r13
0x1800049fd  pop     rdi
0x1800049fe  pop     rsi
0x1800049ff  pop     rbp
0x180004a00  pop     rbx
0x180004a01  retn
0x180004a02  mov     eax, 0C0000017h
0x180004a07  jmp     short loc_1800049F3
0x180004a09  mov     rcx, rbx; hMem
0x180004a0c  call    cs:__imp_LocalFree
0x180004a12  mov     eax, edi
0x180004a14  jmp     short loc_1800049F3
```
