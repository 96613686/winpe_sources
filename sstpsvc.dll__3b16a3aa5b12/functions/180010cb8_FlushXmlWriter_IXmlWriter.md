# FlushXmlWriter(IXmlWriter *)

- ea: `0x180010cb8`
- end: `0x180010e28`
- name: `?FlushXmlWriter@@YAKPEAUIXmlWriter@@@Z`
- size: `368`
- prototype: `unsigned int __fastcall(struct IXmlWriter *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800138c0`
- `0x180014490`

## callees

- `0x18000827c`
- `0x180008360`
- `0x180010cb8`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001d010`

## string_xrefs

- `0x180010d25`: `WriteConfigToXmlFile: WriteFullEndElement of IXmlWriter object failed with error %d`
- `0x180010d5e`: `WriteConfigToXmlFile: WriteFullEndElement of IXmlWriter object failed with error %d`
- `0x180010d85`: `WriteConfigToXmlFile: WriteEndDocument of IXmlWriter object failed with error %d`
- `0x180010daf`: `WriteConfigToXmlFile: Flush of IXmlWriter object failed with error %d`

## pseudocode

```c
__int64 __fastcall FlushXmlWriter(struct IXmlWriter *a1)
{
  unsigned int v2; // eax
  int v3; // ebx
  const wchar_t *v4; // rdx
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v7[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  v2 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
  v3 = v2;
  if ( v2 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_16;
    LOWORD(v6) = 0;
    FormatRRASErrorString(
      &v6,
      L"WriteConfigToXmlFile: WriteFullEndElement of IXmlWriter object failed with error %d",
      v2);
  }
  else
  {
    v3 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteFullEndElement)(a1);
    if ( v3 )
    {
      if ( (byte_18002D803 & 8) == 0 )
        goto LABEL_16;
      v4 = L"WriteConfigToXmlFile: WriteFullEndElement of IXmlWriter object failed with error %d";
    }
    else
    {
      v3 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteEndDocument)(a1);
      if ( v3 )
      {
        if ( (byte_18002D803 & 8) == 0 )
          goto LABEL_16;
        v4 = L"WriteConfigToXmlFile: WriteEndDocument of IXmlWriter object failed with error %d";
      }
      else
      {
        v3 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->Flush)(a1);
        if ( !v3 || (byte_18002D803 & 8) == 0 )
          goto LABEL_16;
        v4 = L"WriteConfigToXmlFile: Flush of IXmlWriter object failed with error %d";
      }
    }
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, v4, (unsigned int)v3);
  }
  if ( (byte_18002D803 & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
LABEL_16:
  result = 0;
  if ( v3 < 0 )
  {
    result = (unsigned __int16)v3;
    if ( (v3 & 0x1FFF0000) != 0x70000 )
      return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x180010cb8  mov     [rsp-8+arg_8], rbx
0x180010cbd  mov     [rsp-8+arg_10], rdi
0x180010cc2  push    rbp
0x180010cc3  lea     rbp, [rsp-730h]
0x180010ccb  sub     rsp, 830h
0x180010cd2  mov     rax, cs:__security_cookie
0x180010cd9  xor     rax, rsp
0x180010cdc  mov     [rbp+730h+var_10], rax
0x180010ce3  mov     rdi, rcx
0x180010ce6  xor     eax, eax
0x180010ce8  lea     rcx, [rsp+830h+var_80C]; void *
0x180010ced  mov     [rsp+830h+var_810], eax
0x180010cf1  xor     edx, edx; Val
0x180010cf3  mov     r8d, 7FCh; Size
0x180010cf9  call    memset_0
0x180010cfe  mov     rax, [rdi]
0x180010d01  mov     rcx, rdi
0x180010d04  mov     rax, [rax+88h]
0x180010d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d10  mov     ebx, eax
0x180010d12  test    eax, eax
0x180010d14  jz      short loc_180010D39
0x180010d16  test    cs:byte_18002D803, 8
0x180010d1d  jz      loc_180010DEB
0x180010d23  xor     ecx, ecx
0x180010d25  lea     rdx, aWriteconfigtox_1; "WriteConfigToXmlFile: WriteFullEndEleme"...
0x180010d2c  mov     word ptr [rsp+830h+var_810], cx
0x180010d31  mov     r8d, eax
0x180010d34  jmp     loc_180010DC0
0x180010d39  mov     rax, [rdi]
0x180010d3c  mov     rcx, rdi
0x180010d3f  mov     rax, [rax+88h]
0x180010d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d4b  mov     ebx, eax
0x180010d4d  test    eax, eax
0x180010d4f  jz      short loc_180010D67
0x180010d51  test    cs:byte_18002D803, 8
0x180010d58  jz      loc_180010DEB
0x180010d5e  lea     rdx, aWriteconfigtox_1; "WriteConfigToXmlFile: WriteFullEndEleme"...
0x180010d65  jmp     short loc_180010DB6
0x180010d67  mov     rax, [rdi]
0x180010d6a  mov     rcx, rdi
0x180010d6d  mov     rax, [rax+70h]
0x180010d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d76  mov     ebx, eax
0x180010d78  test    eax, eax
0x180010d7a  jz      short loc_180010D8E
0x180010d7c  test    cs:byte_18002D803, 8
0x180010d83  jz      short loc_180010DEB
0x180010d85  lea     rdx, aWriteconfigtox; "WriteConfigToXmlFile: WriteEndDocument "...
0x180010d8c  jmp     short loc_180010DB6
0x180010d8e  mov     rax, [rdi]
0x180010d91  mov     rcx, rdi
0x180010d94  mov     rax, [rax+0F8h]
0x180010d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010da0  mov     ebx, eax
0x180010da2  test    eax, eax
0x180010da4  jz      short loc_180010DEB
0x180010da6  test    cs:byte_18002D803, 8
0x180010dad  jz      short loc_180010DEB
0x180010daf  lea     rdx, aWriteconfigtox_0; "WriteConfigToXmlFile: Flush of IXmlWrit"...
0x180010db6  xor     eax, eax
0x180010db8  mov     r8d, ebx
0x180010dbb  mov     word ptr [rsp+830h+var_810], ax
0x180010dc0  lea     rcx, [rsp+830h+var_810]
0x180010dc5  call    FormatRRASErrorString
0x180010dca  test    cs:byte_18002D803, 8
0x180010dd1  jz      short loc_180010DEB
0x180010dd3  lea     r8, [rsp+830h+var_810]
0x180010dd8  lea     rdx, RasSSTPSvcTraceError
0x180010ddf  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180010de6  call    McTemplateU0z_EventWriteTransfer
0x180010deb  xor     eax, eax
0x180010ded  test    ebx, ebx
0x180010def  jns     short loc_180010E04
0x180010df1  mov     eax, ebx
0x180010df3  and     eax, 1FFF0000h
0x180010df8  cmp     eax, 70000h
0x180010dfd  movzx   eax, bx
0x180010e00  jz      short loc_180010E04
0x180010e02  mov     eax, ebx
0x180010e04  mov     rcx, [rbp+730h+var_10]
0x180010e0b  xor     rcx, rsp; StackCookie
0x180010e0e  call    __security_check_cookie
0x180010e13  lea     r11, [rsp+830h+var_s0]
0x180010e1b  mov     rbx, [r11+18h]
0x180010e1f  mov     rdi, [r11+20h]
0x180010e23  mov     rsp, r11
0x180010e26  pop     rbp
0x180010e27  retn
```
