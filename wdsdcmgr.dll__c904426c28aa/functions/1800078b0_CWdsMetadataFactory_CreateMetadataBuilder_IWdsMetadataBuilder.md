# CWdsMetadataFactory::CreateMetadataBuilder(IWdsMetadataBuilder * *)

- ea: `0x1800078b0`
- end: `0x180007950`
- name: `?CreateMetadataBuilder@CWdsMetadataFactory@@UEAAJPEAPEAUIWdsMetadataBuilder@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(CWdsMetadataFactory *__hidden this, struct IWdsMetadataBuilder **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800078b0`
- `0x18000a5e8`
- `0x18000e504`
- `0x180014ee0`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall CWdsMetadataFactory::CreateMetadataBuilder(
        CWdsMetadataFactory *this,
        struct IWdsMetadataBuilder **a2)
{
  unsigned int v3; // ebx
  const char *v4; // rdx
  int v5; // eax
  CWdsComMetadataBuilder *v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-50h] BYREF
  int v9; // [rsp+28h] [rbp-48h]
  int v10; // [rsp+2Ch] [rbp-44h]
  __int64 v11; // [rsp+38h] [rbp-38h]
  int v12; // [rsp+40h] [rbp-30h]
  int v13; // [rsp+44h] [rbp-2Ch]
  __int64 v14; // [rsp+50h] [rbp-20h]
  int v15; // [rsp+58h] [rbp-18h]
  int v16; // [rsp+5Ch] [rbp-14h]
  CWdsComMetadataBuilder *v17; // [rsp+90h] [rbp+20h] BYREF

  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v3 = CWdsComMetadataBuilder::CreateInstance((struct CWdsMetadata *)&v8, &v17);
  v5 = ElValidateHr(v3, v4, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsmetadatafactory.cpp", 0x86u);
  v6 = v17;
  if ( v5 >= 0 )
  {
    *a2 = v17;
    v6 = 0;
  }
  if ( v6 )
    (*(void (__fastcall **)(CWdsComMetadataBuilder *))(*(_QWORD *)v6 + 16LL))(v6);
  CWdsMetadata::~CWdsMetadata((CWdsMetadata *)&v8);
  return v3;
}

```

## disassembly

```asm
0x1800078b0  mov     [rsp-8+arg_0], rbx
0x1800078b5  mov     [rsp-8+arg_8], rdi
0x1800078ba  push    rbp
0x1800078bb  mov     rbp, rsp
0x1800078be  sub     rsp, 70h
0x1800078c2  and     [rbp+var_50], 0
0x1800078c7  lea     rcx, [rbp+var_50]; struct CWdsMetadata *
0x1800078cb  and     [rbp+var_48], 0
0x1800078cf  mov     rdi, rdx
0x1800078d2  and     [rbp+var_44], 0
0x1800078d6  lea     rdx, [rbp+arg_10]
0x1800078da  and     [rbp+var_38], 0
0x1800078df  and     [rbp+var_30], 0
0x1800078e3  and     [rbp+var_2C], 0
0x1800078e7  and     [rbp+var_20], 0
0x1800078ec  and     [rbp+var_18], 0
0x1800078f0  and     [rbp+var_14], 0
0x1800078f4  and     [rbp+arg_10], 0
0x1800078f9  call    ?CreateInstance@CWdsComMetadataBuilder@@SAJPEBVCWdsMetadata@@PEAPEAV?$CComObject@VCWdsComMetadataBuilder@@@ATL@@@Z; CWdsComMetadataBuilder::CreateInstance(CWdsMetadata const *,ATL::CComObject<CWdsComMetadataBuilder> * *)
0x1800078fe  mov     r9d, 86h; unsigned int
0x180007904  lea     r8, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x18000790b  mov     ecx, eax; int
0x18000790d  mov     ebx, eax
0x18000790f  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180007914  mov     rcx, [rbp+arg_10]
0x180007918  test    eax, eax
0x18000791a  js      short loc_180007921
0x18000791c  mov     [rdi], rcx
0x18000791f  xor     ecx, ecx
0x180007921  test    rcx, rcx
0x180007924  jz      short loc_180007933
0x180007926  mov     rax, [rcx]
0x180007929  mov     rax, [rax+10h]
0x18000792d  call    cs:__guard_dispatch_icall_fptr
0x180007933  lea     rcx, [rbp+var_50]; this
0x180007937  call    ??1CWdsMetadata@@QEAA@XZ; CWdsMetadata::~CWdsMetadata(void)
0x18000793c  lea     r11, [rsp+70h+var_s0]
0x180007941  mov     eax, ebx
0x180007943  mov     rbx, [r11+10h]
0x180007947  mov     rdi, [r11+18h]
0x18000794b  mov     rsp, r11
0x18000794e  pop     rbp
0x18000794f  retn
```
