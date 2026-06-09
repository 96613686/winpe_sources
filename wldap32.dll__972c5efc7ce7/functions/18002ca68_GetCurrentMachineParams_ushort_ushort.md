# GetCurrentMachineParams(ushort * *,ushort * *)

- ea: `0x18002ca68`
- end: `0x18002cb8a`
- name: `?GetCurrentMachineParams@@YAKPEAPEAG0@Z`
- size: `290`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002376c`

## callees

- `0x18000b440`
- `0x18001ce90`
- `0x180022e80`
- `0x18002ca68`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002cb28`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002cb5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002cb28`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18002cb5f`
- `ntdll!RtlGetNtProductType` at `0x18002caa9`
- `ntdll!RtlGetNtProductType` at `0x18002caa9`

## pseudocode

```c
__int64 __fastcall GetCurrentMachineParams(unsigned __int16 **a1, unsigned __int16 **a2)
{
  unsigned int v5; // ebx
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // rax
  WCHAR Buffer; // [rsp+40h] [rbp+8h] BYREF
  DWORD nSize; // [rsp+50h] [rbp+18h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+58h] [rbp+20h] BYREF

  ProductType = 0;
  if ( !a1 )
    return 82;
  if ( !a2 )
    return 82;
  *a1 = 0;
  *a2 = 0;
  if ( !RtlGetNtProductType(&ProductType) )
    return 82;
  if ( ProductType == NtProductLanManNt )
  {
    v6 = (unsigned __int16 *)ldap_dup_stringW((void *)L"localhost");
    *a1 = v6;
    if ( v6 )
    {
      nSize = 0;
      Buffer = 0;
      GetComputerNameExW(ComputerNameNetBIOS, &Buffer, &nSize);
      if ( !nSize )
      {
LABEL_15:
        v5 = 82;
        goto LABEL_7;
      }
      v7 = (unsigned __int16 *)ldapMalloc(2 * nSize + 2, 1953712204);
      *a2 = v7;
      if ( v7 )
      {
        if ( GetComputerNameExW(ComputerNameNetBIOS, v7, &nSize) )
          return 0;
        goto LABEL_15;
      }
    }
    v5 = 90;
    goto LABEL_7;
  }
  v5 = 52;
LABEL_7:
  ldapFree(*a2, 1953712204);
  ldapFree(*a1, 1953712204);
  *a2 = 0;
  *a1 = 0;
  return v5;
}

```

## disassembly

```asm
0x18002ca68  push    rbx
0x18002ca6a  push    rsi
0x18002ca6b  push    rdi
0x18002ca6c  sub     rsp, 20h
0x18002ca70  mov     [rsp+38h+ProductType], 0
0x18002ca78  mov     rdi, rdx
0x18002ca7b  mov     rsi, rcx
0x18002ca7e  test    rcx, rcx
0x18002ca81  jnz     short loc_18002CA91
0x18002ca83  mov     eax, 52h ; 'R'
0x18002ca88  add     rsp, 20h
0x18002ca8c  pop     rdi
0x18002ca8d  pop     rsi
0x18002ca8e  pop     rbx
0x18002ca8f  retn
0x18002ca91  test    rdi, rdi
0x18002ca94  jz      short loc_18002CA83
0x18002ca96  mov     qword ptr [rcx], 0
0x18002ca9d  lea     rcx, [rsp+38h+ProductType]; ProductType
0x18002caa2  mov     qword ptr [rdx], 0
0x18002caa9  call    cs:__imp_RtlGetNtProductType
0x18002cab0  nop     dword ptr [rax+rax+00h]
0x18002cab5  test    al, al
0x18002cab7  jz      short loc_18002CA83
0x18002cab9  cmp     [rsp+38h+ProductType], 2
0x18002cabe  jz      short loc_18002CAF1
0x18002cac0  mov     ebx, 34h ; '4'
0x18002cac5  mov     rcx, [rdi]
0x18002cac8  mov     edx, 7473484Ch
0x18002cacd  call    ldapFree
0x18002cad2  mov     rcx, [rsi]
0x18002cad5  mov     edx, 7473484Ch
0x18002cada  call    ldapFree
0x18002cadf  mov     qword ptr [rdi], 0
0x18002cae6  mov     qword ptr [rsi], 0
0x18002caed  mov     eax, ebx
0x18002caef  jmp     short loc_18002CA88
0x18002caf1  xor     edx, edx
0x18002caf3  lea     rcx, aLocalhost; "localhost"
0x18002cafa  mov     r8d, 7473484Ch
0x18002cb00  call    ldap_dup_stringW
0x18002cb05  mov     [rsi], rax
0x18002cb08  test    rax, rax
0x18002cb0b  jz      short loc_18002CB76
0x18002cb0d  xor     eax, eax
0x18002cb0f  mov     [rsp+38h+nSize], 0
0x18002cb17  lea     r8, [rsp+38h+nSize]; nSize
0x18002cb1c  mov     [rsp+38h+Buffer], ax
0x18002cb21  lea     rdx, [rsp+38h+Buffer]; lpBuffer
0x18002cb26  xor     ecx, ecx; NameType
0x18002cb28  call    cs:__imp_GetComputerNameExW
0x18002cb2f  nop     dword ptr [rax+rax+00h]
0x18002cb34  mov     ecx, [rsp+38h+nSize]
0x18002cb38  test    ecx, ecx
0x18002cb3a  jz      short loc_18002CB80
0x18002cb3c  lea     ecx, ds:2[rcx*2]
0x18002cb43  mov     edx, 7473484Ch
0x18002cb48  call    ldapMalloc
0x18002cb4d  mov     [rdi], rax
0x18002cb50  test    rax, rax
0x18002cb53  jz      short loc_18002CB76
0x18002cb55  lea     r8, [rsp+38h+nSize]; nSize
0x18002cb5a  mov     rdx, rax; lpBuffer
0x18002cb5d  xor     ecx, ecx; NameType
0x18002cb5f  call    cs:__imp_GetComputerNameExW
0x18002cb66  nop     dword ptr [rax+rax+00h]
0x18002cb6b  test    eax, eax
0x18002cb6d  jz      short loc_18002CB80
0x18002cb6f  xor     ebx, ebx
0x18002cb71  jmp     loc_18002CAED
0x18002cb76  mov     ebx, 5Ah ; 'Z'
0x18002cb7b  jmp     loc_18002CAC5
0x18002cb80  mov     ebx, 52h ; 'R'
0x18002cb85  jmp     loc_18002CAC5
```
