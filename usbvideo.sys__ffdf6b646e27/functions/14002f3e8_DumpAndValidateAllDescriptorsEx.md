# DumpAndValidateAllDescriptorsEx

- ea: `0x14002f3e8`
- end: `0x14002f587`
- name: `DumpAndValidateAllDescriptorsEx`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140015e60`

## callees

- `0x140020704`
- `0x14002f3e8`
- `0x14002f8cc`
- `0x14002fd58`
- `0x140030208`
- `0x1400304ac`
- `0x14003580c`
- `0x140037068`

## string_xrefs

- `0x14002f549`: `Config descriptor has more than desired data.`
- `0x14002f416`: `Wrong Descriptor Type for USB_CONFIGURATION_DESCRIPTOR.`
- `0x14002f532`: `Invalid Interface Descriptor`
- `0x14002f53b`: `Invalid Config Descriptor`
- `0x14002f497`: `Invalid Class Specific Endpoint Descriptor`
- `0x14002f4db`: `Invalid Endpoint Descriptor`
- `0x14002f50d`: `Invalid Generic Descriptor`

## pseudocode

```c
__int64 __fastcall DumpAndValidateAllDescriptorsEx(unsigned __int8 *a1, __int64 a2)
{
  bool v3; // zf
  unsigned __int8 *v4; // rdi
  int v5; // ebx
  const wchar_t *v6; // rsi
  char v7; // r12
  int v8; // r15d
  unsigned __int64 v9; // rbp
  __int16 v11; // [rsp+60h] [rbp+8h] BYREF

  v3 = a1[1] == 2;
  v4 = a1;
  v11 = 0;
  if ( v3 )
  {
    v7 = 0;
    v8 = 0;
    v5 = 0;
    v6 = 0;
    v9 = (unsigned __int64)&a1[*((unsigned __int16 *)a1 + 1)];
    while ( 1 )
    {
      if ( (unsigned __int64)v4 >= v9 )
        return (unsigned int)v5;
      if ( (unsigned __int64)(v4 + 2) > v9 || (unsigned __int64)&v4[*v4] > v9 )
      {
        v5 = -1073741823;
        v6 = L"Config descriptor has more than desired data.";
LABEL_29:
        if ( v7 )
          return (unsigned int)v5;
        goto LABEL_30;
      }
      switch ( v4[1] )
      {
        case 2u:
          v5 = DumpAndValidateConfigDescriptor(v4, v9);
          if ( v5 < 0 )
          {
            v6 = L"Invalid Config Descriptor";
            goto LABEL_29;
          }
          break;
        case 3u:
          goto LABEL_21;
        case 4u:
          v5 = DumpAndValidateInterfaceDescriptor(v4, v9);
          if ( v5 < 0 )
          {
            v6 = L"Invalid Interface Descriptor";
            goto LABEL_29;
          }
          v8 = v4[6];
          break;
        case 5u:
          v5 = DumpAndValidateEndpointDescriptor(v4, v9);
          if ( v5 < 0 )
          {
            v6 = L"Invalid Endpoint Descriptor";
            goto LABEL_29;
          }
          break;
        case 0x24u:
          v5 = DumpAndValidateClassSpecInterfaceDescriptorEx((_DWORD)v4, v9, v8, (unsigned int)&v11, a2);
          v7 = 1;
          if ( v5 < 0 )
            goto LABEL_29;
          break;
        case 0x25u:
          v5 = DumpAndValidateClassSpecificEndpointDescriptor(v4, v9);
          if ( v5 < 0 )
          {
            v6 = L"Invalid Class Specific Endpoint Descriptor";
            goto LABEL_29;
          }
          break;
        default:
LABEL_21:
          v5 = DumpAndValidateGenericDescriptor(v4, v9);
          if ( v5 < 0 )
          {
            v6 = L"Invalid Generic Descriptor";
            goto LABEL_29;
          }
          break;
      }
      v4 += *v4;
    }
  }
  v5 = -1073741823;
  v6 = L"Wrong Descriptor Type for USB_CONFIGURATION_DESCRIPTOR.";
LABEL_30:
  if ( a2 )
    ReportInvalidConfigurationTelemetry(a2, (unsigned int)v5, v6);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002f3e8  mov     [rsp+arg_8], rbx
0x14002f3ed  mov     [rsp+arg_10], rbp
0x14002f3f2  push    rsi
0x14002f3f3  push    rdi
0x14002f3f4  push    r12
0x14002f3f6  push    r14
0x14002f3f8  push    r15
0x14002f3fa  sub     rsp, 30h
0x14002f3fe  xor     eax, eax
0x14002f400  mov     r14, rdx
0x14002f403  cmp     byte ptr [rcx+1], 2
0x14002f407  mov     rdi, rcx
0x14002f40a  mov     [rsp+58h+arg_0], ax
0x14002f40f  jz      short loc_14002F422
0x14002f411  mov     ebx, 0C0000001h
0x14002f416  lea     rsi, aWrongDescripto; "Wrong Descriptor Type for USB_CONFIGURA"...
0x14002f41d  jmp     loc_14002F55B
0x14002f422  movzx   ebp, word ptr [rcx+2]
0x14002f426  xor     r12b, r12b
0x14002f429  xor     r15d, r15d
0x14002f42c  xor     ebx, ebx
0x14002f42e  xor     esi, esi
0x14002f430  add     rbp, rcx
0x14002f433  cmp     rdi, rbp
0x14002f436  jnb     loc_14002F552
0x14002f43c  lea     rax, [rdi+2]
0x14002f440  cmp     rax, rbp
0x14002f443  ja      loc_14002F544
0x14002f449  movzx   eax, byte ptr [rdi]
0x14002f44c  add     rax, rdi
0x14002f44f  cmp     rax, rbp
0x14002f452  ja      loc_14002F544
0x14002f458  movzx   ecx, byte ptr [rdi+1]
0x14002f45c  sub     ecx, 2
0x14002f45f  jz      loc_14002F516
0x14002f465  sub     ecx, 1
0x14002f468  jz      loc_14002F4FC
0x14002f46e  sub     ecx, 1
0x14002f471  jz      short loc_14002F4E4
0x14002f473  sub     ecx, 1
0x14002f476  jz      short loc_14002F4CA
0x14002f478  sub     ecx, 1Fh
0x14002f47b  jz      short loc_14002F4A3
0x14002f47d  cmp     ecx, 1
0x14002f480  jnz     short loc_14002F4FC
0x14002f482  mov     rdx, rbp
0x14002f485  mov     rcx, rdi
0x14002f488  call    DumpAndValidateClassSpecificEndpointDescriptor
0x14002f48d  mov     ebx, eax
0x14002f48f  test    eax, eax
0x14002f491  jns     loc_14002F527
0x14002f497  lea     rsi, aInvalidClassSp; "Invalid Class Specific Endpoint Descrip"...
0x14002f49e  jmp     loc_14002F556
0x14002f4a3  lea     r9, [rsp+58h+arg_0]
0x14002f4a8  mov     [rsp+58h+var_38], r14
0x14002f4ad  mov     r8d, r15d
0x14002f4b0  mov     rdx, rbp
0x14002f4b3  mov     rcx, rdi
0x14002f4b6  call    DumpAndValidateClassSpecInterfaceDescriptorEx
0x14002f4bb  mov     ebx, eax
0x14002f4bd  mov     r12b, 1
0x14002f4c0  test    eax, eax
0x14002f4c2  js      loc_14002F556
0x14002f4c8  jmp     short loc_14002F527
0x14002f4ca  mov     rdx, rbp
0x14002f4cd  mov     rcx, rdi
0x14002f4d0  call    DumpAndValidateEndpointDescriptor
0x14002f4d5  mov     ebx, eax
0x14002f4d7  test    eax, eax
0x14002f4d9  jns     short loc_14002F527
0x14002f4db  lea     rsi, aInvalidEndpoin; "Invalid Endpoint Descriptor"
0x14002f4e2  jmp     short loc_14002F556
0x14002f4e4  mov     rdx, rbp
0x14002f4e7  mov     rcx, rdi
0x14002f4ea  call    DumpAndValidateInterfaceDescriptor
0x14002f4ef  mov     ebx, eax
0x14002f4f1  test    eax, eax
0x14002f4f3  js      short loc_14002F532
0x14002f4f5  movzx   r15d, byte ptr [rdi+6]
0x14002f4fa  jmp     short loc_14002F527
0x14002f4fc  mov     rdx, rbp
0x14002f4ff  mov     rcx, rdi
0x14002f502  call    DumpAndValidateGenericDescriptor
0x14002f507  mov     ebx, eax
0x14002f509  test    eax, eax
0x14002f50b  jns     short loc_14002F527
0x14002f50d  lea     rsi, aInvalidGeneric; "Invalid Generic Descriptor"
0x14002f514  jmp     short loc_14002F556
0x14002f516  mov     rdx, rbp
0x14002f519  mov     rcx, rdi
0x14002f51c  call    DumpAndValidateConfigDescriptor
0x14002f521  mov     ebx, eax
0x14002f523  test    eax, eax
0x14002f525  js      short loc_14002F53B
0x14002f527  movzx   eax, byte ptr [rdi]
0x14002f52a  add     rdi, rax
0x14002f52d  jmp     loc_14002F433
0x14002f532  lea     rsi, aInvalidInterfa; "Invalid Interface Descriptor"
0x14002f539  jmp     short loc_14002F556
0x14002f53b  lea     rsi, aInvalidConfigD; "Invalid Config Descriptor"
0x14002f542  jmp     short loc_14002F556
0x14002f544  mov     ebx, 0C0000001h
0x14002f549  lea     rsi, aConfigDescript; "Config descriptor has more than desired"...
0x14002f550  jmp     short loc_14002F556
0x14002f552  test    ebx, ebx
0x14002f554  jns     short loc_14002F56D
0x14002f556  test    r12b, r12b
0x14002f559  jnz     short loc_14002F56D
0x14002f55b  test    r14, r14
0x14002f55e  jz      short loc_14002F56D
0x14002f560  mov     r8, rsi
0x14002f563  mov     edx, ebx
0x14002f565  mov     rcx, r14
0x14002f568  call    ReportInvalidConfigurationTelemetry
0x14002f56d  mov     rbp, [rsp+58h+arg_10]
0x14002f572  mov     eax, ebx
0x14002f574  mov     rbx, [rsp+58h+arg_8]
0x14002f579  add     rsp, 30h
0x14002f57d  pop     r15
0x14002f57f  pop     r14
0x14002f581  pop     r12
0x14002f583  pop     rdi
0x14002f584  pop     rsi
0x14002f585  retn
```
