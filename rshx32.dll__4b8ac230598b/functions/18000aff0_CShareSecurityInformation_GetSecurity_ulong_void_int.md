# CShareSecurityInformation::GetSecurity(ulong,void * *,int)

- ea: `0x18000aff0`
- end: `0x18000b09c`
- name: `?GetSecurity@CShareSecurityInformation@@UEAAJKPEAPEAXH@Z`
- size: `172`
- prototype: `__int64 __fastcall(CShareSecurityInformation *this, int, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000aff0`
- `0x18001d322`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b05c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000b05c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000b04d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000b04d`

## pseudocode

```c
__int64 __fastcall CShareSecurityInformation::GetSecurity(CShareSecurityInformation *this, int a2, void **a3)
{
  __int64 result; // rax
  SIZE_T SecurityDescriptorLength; // rsi
  HLOCAL v7; // rax
  signed __int32 v8[10]; // [rsp+0h] [rbp-28h] BYREF

  if ( *((_QWORD *)this + 29) )
  {
    result = *((unsigned int *)this + 60);
    _InterlockedOr(v8, 0);
    if ( !*((_QWORD *)this + 32) )
      return result;
  }
  else if ( !*((_QWORD *)this + 32) )
  {
    return 2147500035LL;
  }
  if ( !a3 || a2 != 4 )
    return 2147942487LL;
  *a3 = 0;
  SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 32));
  v7 = LocalAlloc(0x40u, SecurityDescriptorLength);
  *a3 = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, *((const void **)this + 32), SecurityDescriptorLength);
  return 0;
}

```

## disassembly

```asm
0x18000aff0  mov     [rsp+arg_0], rbx
0x18000aff5  mov     [rsp+arg_8], rsi
0x18000affa  push    rdi
0x18000affb  sub     rsp, 20h
0x18000afff  cmp     qword ptr [rcx+0E8h], 0
0x18000b007  mov     rdi, r8
0x18000b00a  mov     rbx, rcx
0x18000b00d  jnz     short loc_18000B020
0x18000b00f  cmp     qword ptr [rcx+100h], 0
0x18000b017  jnz     short loc_18000B035
0x18000b019  mov     eax, 80004003h
0x18000b01e  jmp     short loc_18000B08C
0x18000b020  mov     eax, [rcx+0F0h]
0x18000b026  lock or [rsp+28h+var_28], 0
0x18000b02b  cmp     qword ptr [rcx+100h], 0
0x18000b033  jz      short loc_18000B08C
0x18000b035  test    rdi, rdi
0x18000b038  jz      short loc_18000B087
0x18000b03a  cmp     edx, 4
0x18000b03d  jnz     short loc_18000B087
0x18000b03f  mov     qword ptr [r8], 0
0x18000b046  mov     rcx, [rcx+100h]; pSecurityDescriptor
0x18000b04d  call    cs:__imp_GetSecurityDescriptorLength
0x18000b053  mov     edx, eax; uBytes
0x18000b055  mov     ecx, 40h ; '@'; uFlags
0x18000b05a  mov     esi, eax
0x18000b05c  call    cs:__imp_LocalAlloc
0x18000b062  mov     [rdi], rax
0x18000b065  test    rax, rax
0x18000b068  jnz     short loc_18000B071
0x18000b06a  mov     eax, 8007000Eh
0x18000b06f  jmp     short loc_18000B08C
0x18000b071  mov     rdx, [rbx+100h]; Src
0x18000b078  mov     r8, rsi; Size
0x18000b07b  mov     rcx, rax; void *
0x18000b07e  call    memcpy_0
0x18000b083  xor     eax, eax
0x18000b085  jmp     short loc_18000B08C
0x18000b087  mov     eax, 80070057h
0x18000b08c  mov     rbx, [rsp+28h+arg_0]
0x18000b091  mov     rsi, [rsp+28h+arg_8]
0x18000b096  add     rsp, 20h
0x18000b09a  pop     rdi
0x18000b09b  retn
```
