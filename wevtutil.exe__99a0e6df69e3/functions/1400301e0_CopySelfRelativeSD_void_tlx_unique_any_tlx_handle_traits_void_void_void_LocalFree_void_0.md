# CopySelfRelativeSD(void *,tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)

- ea: `0x1400301e0`
- end: `0x140030293`
- name: `?CopySelfRelativeSD@@YAKPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003029c`

## callees

- `0x1400301e0`
- `0x140031828`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030245`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003025c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14003025c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003026d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140030204`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14003026d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140030250`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x140030250`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140030212`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x140030212`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x14003023b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x14003023b`

## pseudocode

```c
DWORD __fastcall CopySelfRelativeSD(void *Src, void **a2)
{
  void *v4; // rcx
  SIZE_T SecurityDescriptorLength; // rsi
  HLOCAL v7; // rax
  void *v8; // rcx
  WORD pControl; // [rsp+30h] [rbp+8h] BYREF
  DWORD dwRevision; // [rsp+38h] [rbp+10h] BYREF

  v4 = *a2;
  *a2 = 0;
  if ( v4 )
    LocalFree(v4);
  if ( Src )
  {
    if ( !IsValidSecurityDescriptor(Src) )
      return 13;
    pControl = 0;
    dwRevision = 0;
    if ( !GetSecurityDescriptorControl(Src, &pControl, &dwRevision) )
      return GetLastError();
    SecurityDescriptorLength = GetSecurityDescriptorLength(Src);
    v7 = LocalAlloc(0, SecurityDescriptorLength);
    v8 = *a2;
    *a2 = v7;
    if ( v8 )
      LocalFree(v8);
    memcpy_0(*a2, Src, SecurityDescriptorLength);
  }
  return 0;
}

```

## disassembly

```asm
0x1400301e0  mov     [rsp+arg_10], rbx
0x1400301e5  mov     [rsp+arg_18], rsi
0x1400301ea  push    rdi
0x1400301eb  sub     rsp, 20h
0x1400301ef  mov     rbx, rcx
0x1400301f2  mov     rdi, rdx
0x1400301f5  mov     rcx, [rdx]; hMem
0x1400301f8  mov     qword ptr [rdx], 0
0x1400301ff  test    rcx, rcx
0x140030202  jz      short loc_14003020A
0x140030204  call    cs:__imp_LocalFree
0x14003020a  test    rbx, rbx
0x14003020d  jz      short loc_140030281
0x14003020f  mov     rcx, rbx; pSecurityDescriptor
0x140030212  call    cs:__imp_IsValidSecurityDescriptor
0x140030218  test    eax, eax
0x14003021a  jnz     short loc_140030223
0x14003021c  mov     eax, 0Dh
0x140030221  jmp     short loc_140030283
0x140030223  xor     eax, eax
0x140030225  lea     r8, [rsp+28h+dwRevision]; lpdwRevision
0x14003022a  lea     rdx, [rsp+28h+pControl]; pControl
0x14003022f  mov     [rsp+28h+pControl], ax
0x140030234  mov     rcx, rbx; pSecurityDescriptor
0x140030237  mov     [rsp+28h+dwRevision], eax
0x14003023b  call    cs:__imp_GetSecurityDescriptorControl
0x140030241  test    eax, eax
0x140030243  jnz     short loc_14003024D
0x140030245  call    cs:__imp_GetLastError
0x14003024b  jmp     short loc_140030283
0x14003024d  mov     rcx, rbx; pSecurityDescriptor
0x140030250  call    cs:__imp_GetSecurityDescriptorLength
0x140030256  mov     edx, eax; uBytes
0x140030258  xor     ecx, ecx; uFlags
0x14003025a  mov     esi, eax
0x14003025c  call    cs:__imp_LocalAlloc
0x140030262  mov     rcx, [rdi]; hMem
0x140030265  mov     [rdi], rax
0x140030268  test    rcx, rcx
0x14003026b  jz      short loc_140030273
0x14003026d  call    cs:__imp_LocalFree
0x140030273  mov     rcx, [rdi]; void *
0x140030276  mov     r8, rsi; Size
0x140030279  mov     rdx, rbx; Src
0x14003027c  call    memcpy_0
0x140030281  xor     eax, eax
0x140030283  mov     rbx, [rsp+28h+arg_10]
0x140030288  mov     rsi, [rsp+28h+arg_18]
0x14003028d  add     rsp, 20h
0x140030291  pop     rdi
0x140030292  retn
```
