# CWdsMetadataFactory::CreateDeviceManagementHelper(IWdsDeviceManagementHelper * *)

- ea: `0x180007960`
- end: `0x180007a9d`
- name: `?CreateDeviceManagementHelper@CWdsMetadataFactory@@UEAAJPEAPEAUIWdsDeviceManagementHelper@@@Z`
- size: `317`
- prototype: `__int64 __fastcall(CWdsMetadataFactory *__hidden this, struct IWdsDeviceManagementHelper **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001cd0`
- `0x180007960`
- `0x180014ee0`
- `0x180015068`
- `0x180015c9d`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall CWdsMetadataFactory::CreateDeviceManagementHelper(
        CWdsMetadataFactory *this,
        struct IWdsDeviceManagementHelper **a2)
{
  struct IWdsDeviceManagementHelper *v3; // rsi
  unsigned int v4; // ebp
  _DWORD *v5; // rax
  const char *v6; // rdx
  struct IWdsDeviceManagementHelper *v7; // rdi
  int v8; // eax
  struct IWdsDeviceManagementHelper *v9; // rbx
  const char *v10; // rdx

  v3 = 0;
  v4 = -2147024882;
  v5 = operator new(0x40u);
  v7 = (struct IWdsDeviceManagementHelper *)v5;
  if ( v5 )
  {
    v5[2] = 0;
    memset_0(v5 + 4, 0, 0x28u);
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CWdsDeviceManagementHelper>::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  else
  {
    v7 = 0;
  }
  if ( v7 )
  {
    v8 = ATL::CComCriticalSection::Init((struct _RTL_CRITICAL_SECTION *)((char *)v7 + 16));
    if ( v8 >= 0 )
    {
      *((_BYTE *)v7 + 56) = 1;
      v8 = 0;
    }
    v4 = 0;
    if ( v8 < 0 )
      v4 = v8;
    if ( v4 )
    {
      (*(void (__fastcall **)(struct IWdsDeviceManagementHelper *, __int64))(*(_QWORD *)v7 + 32LL))(v7, 1);
      v7 = 0;
    }
  }
  v9 = v7;
  if ( (int)ElValidateHr(v4, v6, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsdevicemanagementhelper.cpp", 0x67u) >= 0 )
  {
    (*(void (__fastcall **)(struct IWdsDeviceManagementHelper *))(*(_QWORD *)v7 + 8LL))(v7);
    v3 = v7;
    v9 = 0;
    v7 = 0;
  }
  if ( v9 )
    (*(void (__fastcall **)(struct IWdsDeviceManagementHelper *))(*(_QWORD *)v7 + 16LL))(v7);
  if ( (int)ElValidateHr(v4, v10, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsmetadatafactory.cpp", 0xABu) >= 0 )
  {
    *a2 = v3;
    v3 = 0;
  }
  if ( v3 )
    (*(void (__fastcall **)(struct IWdsDeviceManagementHelper *))(*(_QWORD *)v3 + 16LL))(v3);
  return v4;
}

```

## disassembly

```asm
0x180007960  mov     [rsp+arg_0], rbx
0x180007965  mov     [rsp+arg_8], rbp
0x18000796a  mov     [rsp+arg_10], rsi
0x18000796f  push    rdi
0x180007970  push    r14
0x180007972  push    r15
0x180007974  sub     rsp, 20h
0x180007978  xor     r15d, r15d
0x18000797b  mov     r14, rdx
0x18000797e  mov     esi, r15d
0x180007981  mov     ebp, 8007000Eh
0x180007986  lea     ecx, [r15+40h]; Size
0x18000798a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000798f  mov     rdi, rax
0x180007992  test    rax, rax
0x180007995  jz      short loc_1800079C5
0x180007997  xor     edx, edx; Val
0x180007999  mov     [rax+8], r15d
0x18000799d  lea     r8d, [r15+28h]; Size
0x1800079a1  lea     rcx, [rax+10h]; void *
0x1800079a5  call    memset_0
0x1800079aa  lea     rax, ??_7?$CComObject@VCWdsDeviceManagementHelper@@@ATL@@6B@; const ATL::CComObject<CWdsDeviceManagementHelper>::`vftable'
0x1800079b1  mov     [rdi+38h], r15b
0x1800079b5  mov     [rdi], rax
0x1800079b8  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800079bf  lock inc dword ptr [rax+0Ch]
0x1800079c3  jmp     short loc_1800079C8
0x1800079c5  mov     rdi, r15
0x1800079c8  test    rdi, rdi
0x1800079cb  jz      short loc_180007A06
0x1800079cd  lea     rcx, [rdi+10h]; this
0x1800079d1  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x1800079d6  test    eax, eax
0x1800079d8  js      short loc_1800079DE
0x1800079da  mov     byte ptr [rdi+38h], 1
0x1800079de  cmovns  eax, r15d
0x1800079e2  mov     ebp, r15d
0x1800079e5  test    eax, eax
0x1800079e7  cmovs   ebp, eax
0x1800079ea  test    ebp, ebp
0x1800079ec  jz      short loc_180007A06
0x1800079ee  mov     rax, [rdi]
0x1800079f1  mov     edx, 1
0x1800079f6  mov     rcx, rdi
0x1800079f9  mov     rax, [rax+20h]
0x1800079fd  call    cs:__guard_dispatch_icall_fptr
0x180007a03  mov     rdi, r15
0x180007a06  mov     r9d, 67h ; 'g'; unsigned int
0x180007a0c  lea     r8, aBaseEcoWdsWdss_2; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180007a13  mov     ecx, ebp; int
0x180007a15  mov     rbx, rdi
0x180007a18  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180007a1d  test    eax, eax
0x180007a1f  js      short loc_180007A3A
0x180007a21  mov     rax, [rdi]
0x180007a24  mov     rcx, rdi
0x180007a27  mov     rax, [rax+8]
0x180007a2b  call    cs:__guard_dispatch_icall_fptr
0x180007a31  mov     rsi, rdi
0x180007a34  mov     rbx, r15
0x180007a37  mov     rdi, r15
0x180007a3a  test    rbx, rbx
0x180007a3d  jz      short loc_180007A4F
0x180007a3f  mov     rax, [rdi]
0x180007a42  mov     rcx, rdi
0x180007a45  mov     rax, [rax+10h]
0x180007a49  call    cs:__guard_dispatch_icall_fptr
0x180007a4f  mov     r9d, 0ABh; unsigned int
0x180007a55  lea     r8, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180007a5c  mov     ecx, ebp; int
0x180007a5e  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180007a63  test    eax, eax
0x180007a65  js      short loc_180007A6D
0x180007a67  mov     [r14], rsi
0x180007a6a  mov     rsi, r15
0x180007a6d  test    rsi, rsi
0x180007a70  jz      short loc_180007A82
0x180007a72  mov     rdx, [rsi]
0x180007a75  mov     rcx, rsi
0x180007a78  mov     rax, [rdx+10h]
0x180007a7c  call    cs:__guard_dispatch_icall_fptr
0x180007a82  mov     rbx, [rsp+38h+arg_0]
0x180007a87  mov     eax, ebp
0x180007a89  mov     rbp, [rsp+38h+arg_8]
0x180007a8e  mov     rsi, [rsp+38h+arg_10]
0x180007a93  add     rsp, 20h
0x180007a97  pop     r15
0x180007a99  pop     r14
0x180007a9b  pop     rdi
0x180007a9c  retn
```
