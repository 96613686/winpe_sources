# HTTP_WRAPPER::SetConfigGroupRequestQueueHandle(unsigned __int64,void *)

- ea: `0x180013400`
- end: `0x180013449`
- name: `?SetConfigGroupRequestQueueHandle@HTTP_WRAPPER@@QEAAK_KPEAX@Z`
- size: `73`
- prototype: `unsigned int(HTTP_WRAPPER *__hidden this, unsigned __int64, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012530`

## callees

- `0x180013400`

## import_xrefs

- `HTTPAPI!HttpSetUrlGroupProperty` at `0x18001343e`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x18001343e`

## pseudocode

```c
ULONG __fastcall HTTP_WRAPPER::SetConfigGroupRequestQueueHandle(HTTP_WRAPPER *this, HTTP_URL_GROUP_ID a2, void *a3)
{
  __int128 *p_PropertyInformation; // rax
  __int64 v4; // rcx
  __int128 PropertyInformation; // [rsp+20h] [rbp-18h] BYREF

  p_PropertyInformation = &PropertyInformation;
  PropertyInformation = 0;
  v4 = 16;
  do
  {
    *(_BYTE *)p_PropertyInformation = 0;
    p_PropertyInformation = (__int128 *)((char *)p_PropertyInformation + 1);
    --v4;
  }
  while ( v4 );
  LODWORD(PropertyInformation) = PropertyInformation | 1;
  *((_QWORD *)&PropertyInformation + 1) = a3;
  return HttpSetUrlGroupProperty(a2, HttpServerBindingProperty, &PropertyInformation, 0x10u);
}

```

## disassembly

```asm
0x180013400  sub     rsp, 38h
0x180013404  xorps   xmm0, xmm0
0x180013407  lea     rax, [rsp+38h+PropertyInformation]
0x18001340c  mov     r9d, 10h; PropertyInformationLength
0x180013412  mov     r10, rdx
0x180013415  movups  [rsp+38h+PropertyInformation], xmm0
0x18001341a  mov     ecx, r9d
0x18001341d  mov     byte ptr [rax], 0
0x180013420  inc     rax
0x180013423  sub     rcx, 1
0x180013427  jnz     short loc_18001341D
0x180013429  or      dword ptr [rsp+38h+PropertyInformation], 1
0x18001342e  lea     edx, [rcx+7]; Property
0x180013431  mov     qword ptr [rsp+38h+PropertyInformation+8], r8
0x180013436  mov     rcx, r10; UrlGroupId
0x180013439  lea     r8, [rsp+38h+PropertyInformation]; PropertyInformation
0x18001343e  call    cs:__imp_HttpSetUrlGroupProperty
0x180013444  add     rsp, 38h
0x180013448  retn
```
