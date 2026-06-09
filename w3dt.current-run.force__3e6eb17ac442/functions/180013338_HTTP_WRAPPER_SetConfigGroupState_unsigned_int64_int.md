# HTTP_WRAPPER::SetConfigGroupState(unsigned __int64,int)

- ea: `0x180013338`
- end: `0x18001336d`
- name: `?SetConfigGroupState@HTTP_WRAPPER@@QEAAK_KH@Z`
- size: `53`
- prototype: `unsigned int(HTTP_WRAPPER *__hidden this, unsigned __int64, int)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012530`
- `0x1800132cc`

## import_xrefs

- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180013362`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180013362`

## pseudocode

```c
ULONG __fastcall HTTP_WRAPPER::SetConfigGroupState(HTTP_WRAPPER *this, HTTP_URL_GROUP_ID a2, int a3)
{
  int PropertyInformation; // [rsp+48h] [rbp+20h] BYREF
  BOOL v5; // [rsp+4Ch] [rbp+24h]

  PropertyInformation = 1;
  v5 = a3 == 0;
  return HttpSetUrlGroupProperty(a2, HttpServerStateProperty, &PropertyInformation, 8u);
}

```

## disassembly

```asm
0x180013338  sub     rsp, 28h
0x18001333c  xor     eax, eax
0x18001333e  mov     [rsp+28h+PropertyInformation], 1
0x180013346  test    r8d, r8d
0x180013349  mov     r9d, 8; PropertyInformationLength
0x18001334f  mov     rcx, rdx; UrlGroupId
0x180013352  lea     r8, [rsp+28h+PropertyInformation]; PropertyInformation
0x180013357  setz    al
0x18001335a  mov     [rsp+28h+arg_1C], eax
0x18001335e  lea     edx, [r9-3]; Property
0x180013362  call    cs:__imp_HttpSetUrlGroupProperty
0x180013368  add     rsp, 28h
0x18001336c  retn
```
