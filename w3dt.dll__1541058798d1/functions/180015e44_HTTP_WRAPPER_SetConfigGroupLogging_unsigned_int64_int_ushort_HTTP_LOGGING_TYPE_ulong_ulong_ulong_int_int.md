# HTTP_WRAPPER::SetConfigGroupLogging(unsigned __int64,int,ushort *,_HTTP_LOGGING_TYPE,ulong,ulong,ulong,int,int)

- ea: `0x180015e44`
- end: `0x180015f3e`
- name: `?SetConfigGroupLogging@HTTP_WRAPPER@@QEAAK_KHPEAGW4_HTTP_LOGGING_TYPE@@KKKHH@Z`
- size: `250`
- prototype: `unsigned int __usercall@<eax>(HTTP_WRAPPER *__hidden this@<rcx>, HTTP_URL_GROUP_ID UrlGroupId@<rdx>, int@<r8d>, unsigned __int16 *@<r9>, enum _HTTP_LOGGING_TYPE, unsigned int, unsigned int, unsigned int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800108c0`
- `0x180012b5c`

## callees

- `0x180015e44`
- `0x180015f44`
- `0x180016072`

## import_xrefs

- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180015f2d`
- `HTTPAPI!HttpSetUrlGroupProperty` at `0x180015f2d`

## string_xrefs

- `0x180015ecd`: `Microsoft Internet Information Services 10.0`

## pseudocode

```c
ULONG __fastcall HTTP_WRAPPER::SetConfigGroupLogging(
        HTTP_WRAPPER *this,
        HTTP_URL_GROUP_ID UrlGroupId,
        int a3,
        unsigned __int16 *a4,
        enum _HTTP_LOGGING_TYPE a5,
        HTTP_LOGGING_ROLLOVER_TYPE a6,
        ULONG a7,
        ULONG a8,
        int a9,
        int a10)
{
  __int64 v14; // r10
  struct _HTTP_LOGGING_INFO *p_PropertyInformation; // rax
  ULONG LoggingFlags; // ecx
  __int64 v17; // rax
  struct _HTTP_LOGGING_INFO PropertyInformation; // [rsp+20h] [rbp-50h] BYREF

  memset_0(&PropertyInformation, 0, sizeof(PropertyInformation));
  v14 = 72;
  p_PropertyInformation = &PropertyInformation;
  do
  {
    *(_BYTE *)&p_PropertyInformation->Flags = 0;
    p_PropertyInformation = (struct _HTTP_LOGGING_INFO *)((char *)p_PropertyInformation + 1);
    --v14;
  }
  while ( v14 );
  if ( a3 )
  {
    *(_DWORD *)&PropertyInformation.Flags |= 1u;
    PropertyInformation.Format = a5;
    PropertyInformation.Fields = a8;
    PropertyInformation.pExtFields = 0;
    *(_DWORD *)&PropertyInformation.NumOfExtFields = 0;
    if ( a5 == 4 )
    {
      HTTP_WRAPPER::SetLoggingInfoW3CEtwType(this, &PropertyInformation);
    }
    else
    {
      LoggingFlags = PropertyInformation.LoggingFlags;
      if ( a10 )
        LoggingFlags = 16;
      PropertyInformation.SoftwareNameLength = 88;
      PropertyInformation.SoftwareName = L"Microsoft Internet Information Services 10.0";
      PropertyInformation.LoggingFlags = LoggingFlags;
      if ( a4 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a4[v17] );
        PropertyInformation.DirectoryName = a4;
        PropertyInformation.DirectoryNameLength = 2 * v17;
      }
      PropertyInformation.RolloverType = a6;
      PropertyInformation.RolloverSize = a7;
      if ( a9 == 1 )
      {
        LoggingFlags |= 1u;
        PropertyInformation.LoggingFlags = LoggingFlags;
      }
      if ( *((_DWORD *)this + 7) == 1 )
        PropertyInformation.LoggingFlags = LoggingFlags | 2;
    }
  }
  return HttpSetUrlGroupProperty(UrlGroupId, HttpServerLoggingProperty, &PropertyInformation, 0x48u);
}

```

## disassembly

```asm
0x180015e44  push    rbp
0x180015e46  push    rbx
0x180015e47  push    rsi
0x180015e48  push    rdi
0x180015e49  push    r14
0x180015e4b  mov     rbp, rsp
0x180015e4e  sub     rsp, 70h
0x180015e52  mov     r14, rdx
0x180015e55  mov     esi, r8d
0x180015e58  xor     edx, edx; Val
0x180015e5a  mov     rdi, rcx
0x180015e5d  lea     rcx, [rbp+PropertyInformation]; void *
0x180015e61  mov     rbx, r9
0x180015e64  lea     r8d, [rdx+48h]; Size
0x180015e68  call    memset_0
0x180015e6d  mov     r10d, 48h ; 'H'
0x180015e73  lea     rax, [rbp+PropertyInformation]
0x180015e77  xor     edx, edx
0x180015e79  mov     [rax], dl
0x180015e7b  inc     rax
0x180015e7e  sub     r10, 1
0x180015e82  jnz     short loc_180015E79
0x180015e84  test    esi, esi
0x180015e86  jz      loc_180015F1C
0x180015e8c  mov     ecx, [rbp+arg_20]
0x180015e8f  or      [rbp+PropertyInformation], 1
0x180015e93  mov     eax, [rbp+arg_38]
0x180015e96  mov     [rbp+var_30], ecx
0x180015e99  mov     [rbp+var_2C], eax
0x180015e9c  mov     [rbp+var_28], rdx
0x180015ea0  mov     [rbp+var_20], edx
0x180015ea3  cmp     ecx, 4
0x180015ea6  jnz     short loc_180015EB6
0x180015ea8  lea     rdx, [rbp+PropertyInformation]; struct _HTTP_LOGGING_INFO *
0x180015eac  mov     rcx, rdi; this
0x180015eaf  call    ?SetLoggingInfoW3CEtwType@HTTP_WRAPPER@@AEAAXPEAU_HTTP_LOGGING_INFO@@@Z; HTTP_WRAPPER::SetLoggingInfoW3CEtwType(_HTTP_LOGGING_INFO *)
0x180015eb4  jmp     short loc_180015F1C
0x180015eb6  cmp     [rbp+arg_48], edx
0x180015eb9  mov     eax, 10h
0x180015ebe  mov     ecx, [rbp+var_4C]
0x180015ec1  cmovnz  ecx, eax
0x180015ec4  mov     eax, 58h ; 'X'
0x180015ec9  mov     [rbp+var_40], ax
0x180015ecd  lea     rax, aMicrosoftInter; "Microsoft Internet Information Services"...
0x180015ed4  mov     [rbp+var_48], rax
0x180015ed8  mov     [rbp+var_4C], ecx
0x180015edb  test    rbx, rbx
0x180015ede  jz      short loc_180015EF8
0x180015ee0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015ee4  inc     rax
0x180015ee7  cmp     [rbx+rax*2], dx
0x180015eeb  jnz     short loc_180015EE4
0x180015eed  add     ax, ax
0x180015ef0  mov     [rbp+var_38], rbx
0x180015ef4  mov     [rbp+var_3E], ax
0x180015ef8  cmp     [rbp+arg_40], 1
0x180015efc  mov     eax, [rbp+arg_28]
0x180015eff  mov     [rbp+var_1C], eax
0x180015f02  mov     eax, [rbp+arg_30]
0x180015f05  mov     [rbp+var_18], eax
0x180015f08  jnz     short loc_180015F10
0x180015f0a  or      ecx, 1
0x180015f0d  mov     [rbp+var_4C], ecx
0x180015f10  cmp     dword ptr [rdi+1Ch], 1
0x180015f14  jnz     short loc_180015F1C
0x180015f16  or      ecx, 2
0x180015f19  mov     [rbp+var_4C], ecx
0x180015f1c  mov     r9d, 48h ; 'H'; PropertyInformationLength
0x180015f22  lea     r8, [rbp+PropertyInformation]; PropertyInformation
0x180015f26  mov     rcx, r14; UrlGroupId
0x180015f29  lea     edx, [r9-47h]; Property
0x180015f2d  call    cs:__imp_HttpSetUrlGroupProperty
0x180015f33  add     rsp, 70h
0x180015f37  pop     r14
0x180015f39  pop     rdi
0x180015f3a  pop     rsi
0x180015f3b  pop     rbx
0x180015f3c  pop     rbp
0x180015f3d  retn
```
