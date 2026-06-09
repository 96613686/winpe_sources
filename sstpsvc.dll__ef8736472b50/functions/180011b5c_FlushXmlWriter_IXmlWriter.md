# FlushXmlWriter(IXmlWriter *)

- ea: `0x180011b5c`
- end: `0x180011ccd`
- name: `?FlushXmlWriter@@YAKPEAUIXmlWriter@@@Z`
- size: `369`
- prototype: `unsigned int __fastcall(struct IXmlWriter *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014900`
- `0x180015500`

## callees

- `0x1800089dc`
- `0x180008b90`
- `0x180011b5c`
- `0x18001d1da`
- `0x18001d210`
- `0x18001e010`

## string_xrefs

- `0x180011bc9`: `WriteConfigToXmlFile: WriteFullEndElement of IXmlWriter object failed with error %d`
- `0x180011c02`: `WriteConfigToXmlFile: WriteFullEndElement of IXmlWriter object failed with error %d`
- `0x180011c29`: `WriteConfigToXmlFile: WriteEndDocument of IXmlWriter object failed with error %d`
- `0x180011c53`: `WriteConfigToXmlFile: Flush of IXmlWriter object failed with error %d`

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
    if ( (byte_18002E903 & 8) == 0 )
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
      if ( (byte_18002E903 & 8) == 0 )
        goto LABEL_16;
      v4 = L"WriteConfigToXmlFile: WriteFullEndElement of IXmlWriter object failed with error %d";
    }
    else
    {
      v3 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->WriteEndDocument)(a1);
      if ( v3 )
      {
        if ( (byte_18002E903 & 8) == 0 )
          goto LABEL_16;
        v4 = L"WriteConfigToXmlFile: WriteEndDocument of IXmlWriter object failed with error %d";
      }
      else
      {
        v3 = ((__int64 (__fastcall *)(struct IXmlWriter *))a1->lpVtbl->Flush)(a1);
        if ( !v3 || (byte_18002E903 & 8) == 0 )
          goto LABEL_16;
        v4 = L"WriteConfigToXmlFile: Flush of IXmlWriter object failed with error %d";
      }
    }
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, v4, (unsigned int)v3);
  }
  if ( (byte_18002E903 & 8) != 0 )
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
0x180011b5c  mov     [rsp-8+arg_8], rbx
0x180011b61  mov     [rsp-8+arg_10], rdi
0x180011b66  push    rbp
0x180011b67  lea     rbp, [rsp-730h]
0x180011b6f  sub     rsp, 830h
0x180011b76  mov     rax, cs:__security_cookie
0x180011b7d  xor     rax, rsp
0x180011b80  mov     [rbp+730h+var_10], rax
0x180011b87  mov     rdi, rcx
0x180011b8a  xor     eax, eax
0x180011b8c  lea     rcx, [rsp+830h+var_80C]; void *
0x180011b91  mov     [rsp+830h+var_810], eax
0x180011b95  xor     edx, edx; Val
0x180011b97  mov     r8d, 7FCh; Size
0x180011b9d  call    memset_0
0x180011ba2  mov     rax, [rdi]
0x180011ba5  mov     rcx, rdi
0x180011ba8  mov     rax, [rax+88h]
0x180011baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bb4  mov     ebx, eax
0x180011bb6  test    eax, eax
0x180011bb8  jz      short loc_180011BDD
0x180011bba  test    cs:byte_18002E903, 8
0x180011bc1  jz      loc_180011C8F
0x180011bc7  xor     ecx, ecx
0x180011bc9  lea     rdx, aWriteconfigtox_1; "WriteConfigToXmlFile: WriteFullEndEleme"...
0x180011bd0  mov     word ptr [rsp+830h+var_810], cx
0x180011bd5  mov     r8d, eax
0x180011bd8  jmp     loc_180011C64
0x180011bdd  mov     rax, [rdi]
0x180011be0  mov     rcx, rdi
0x180011be3  mov     rax, [rax+88h]
0x180011bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bef  mov     ebx, eax
0x180011bf1  test    eax, eax
0x180011bf3  jz      short loc_180011C0B
0x180011bf5  test    cs:byte_18002E903, 8
0x180011bfc  jz      loc_180011C8F
0x180011c02  lea     rdx, aWriteconfigtox_1; "WriteConfigToXmlFile: WriteFullEndEleme"...
0x180011c09  jmp     short loc_180011C5A
0x180011c0b  mov     rax, [rdi]
0x180011c0e  mov     rcx, rdi
0x180011c11  mov     rax, [rax+70h]
0x180011c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c1a  mov     ebx, eax
0x180011c1c  test    eax, eax
0x180011c1e  jz      short loc_180011C32
0x180011c20  test    cs:byte_18002E903, 8
0x180011c27  jz      short loc_180011C8F
0x180011c29  lea     rdx, aWriteconfigtox; "WriteConfigToXmlFile: WriteEndDocument "...
0x180011c30  jmp     short loc_180011C5A
0x180011c32  mov     rax, [rdi]
0x180011c35  mov     rcx, rdi
0x180011c38  mov     rax, [rax+0F8h]
0x180011c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c44  mov     ebx, eax
0x180011c46  test    eax, eax
0x180011c48  jz      short loc_180011C8F
0x180011c4a  test    cs:byte_18002E903, 8
0x180011c51  jz      short loc_180011C8F
0x180011c53  lea     rdx, aWriteconfigtox_0; "WriteConfigToXmlFile: Flush of IXmlWrit"...
0x180011c5a  xor     eax, eax
0x180011c5c  mov     r8d, ebx
0x180011c5f  mov     word ptr [rsp+830h+var_810], ax
0x180011c64  lea     rcx, [rsp+830h+var_810]
0x180011c69  call    FormatRRASErrorString
0x180011c6e  test    cs:byte_18002E903, 8
0x180011c75  jz      short loc_180011C8F
0x180011c77  lea     r8, [rsp+830h+var_810]
0x180011c7c  lea     rdx, RasSSTPSvcTraceError
0x180011c83  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180011c8a  call    McTemplateU0z_EventWriteTransfer
0x180011c8f  xor     eax, eax
0x180011c91  test    ebx, ebx
0x180011c93  jns     short loc_180011CA8
0x180011c95  mov     eax, ebx
0x180011c97  and     eax, 1FFF0000h
0x180011c9c  cmp     eax, 70000h
0x180011ca1  movzx   eax, bx
0x180011ca4  jz      short loc_180011CA8
0x180011ca6  mov     eax, ebx
0x180011ca8  mov     rcx, [rbp+730h+var_10]
0x180011caf  xor     rcx, rsp; StackCookie
0x180011cb2  call    __security_check_cookie
0x180011cb7  lea     r11, [rsp+830h+var_s0]
0x180011cbf  mov     rbx, [r11+18h]
0x180011cc3  mov     rdi, [r11+20h]
0x180011cc7  mov     rsp, r11
0x180011cca  pop     rbp
0x180011ccb  retn
```
