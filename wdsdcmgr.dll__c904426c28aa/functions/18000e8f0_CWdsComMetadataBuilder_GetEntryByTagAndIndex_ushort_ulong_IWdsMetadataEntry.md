# CWdsComMetadataBuilder::GetEntryByTagAndIndex(ushort *,ulong,IWdsMetadataEntry * *)

- ea: `0x18000e8f0`
- end: `0x18000ea8a`
- name: `?GetEntryByTagAndIndex@CWdsComMetadataBuilder@@UEAAJPEAGKPEAPEAUIWdsMetadataEntry@@@Z`
- size: `410`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned int, struct IWdsMetadataEntry **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ae38`
- `0x18000e3e4`
- `0x18000e8f0`
- `0x180011854`
- `0x180014d58`
- `0x180014ee0`
- `0x1800150b8`
- `0x180015cc0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e935`
- `KERNEL32!EnterCriticalSection` at `0x18000e935`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea57`
- `KERNEL32!LeaveCriticalSection` at `0x18000ea57`

## string_xrefs

- `0x18000e957`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000e983`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000e9b9`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000e9ee`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000ea21`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::GetEntryByTagAndIndex(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IWdsMetadataEntry **a4)
{
  void *v4; // rdi
  __int64 v5; // r14
  struct CWdsMetadataEntry *v9; // r12
  const char *v10; // rdx
  unsigned int Instance; // ebx
  signed int InstancesOfTag; // edi
  const char *v13; // rdx
  const char *v14; // rdx
  unsigned int v15; // esi
  const char *v16; // rdx
  void *v18; // [rsp+20h] [rbp-20h] BYREF
  int v19; // [rsp+28h] [rbp-18h]
  unsigned int v20; // [rsp+2Ch] [rbp-14h]

  v4 = 0;
  v5 = a3;
  v19 = 0;
  v20 = 0;
  v18 = 0;
  v9 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( !(unsigned int)ValidateNonEmptyBstr(a2) || !a4 )
  {
    Instance = -2147024809;
    if ( (int)ElValidateHr(-2147024809, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x1B6u) < 0 )
      goto LABEL_19;
  }
  InstancesOfTag = CWdsMetadata::GetInstancesOfTag((char *)this + 64, a2, &v18);
  if ( ElValidateWin32(InstancesOfTag, v13, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x1BAu) )
  {
    Instance = (unsigned __int16)InstancesOfTag | 0x80070000;
    if ( InstancesOfTag <= 0 )
      Instance = InstancesOfTag;
    goto LABEL_7;
  }
  if ( (unsigned int)v5 >= v20 )
  {
    Instance = -2147024809;
    if ( (int)ElValidateHr(-2147024809, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x1BFu) < 0 )
    {
LABEL_7:
      v4 = v18;
      goto LABEL_19;
    }
  }
  v4 = v18;
  v15 = 0;
  if ( (unsigned int)v5 < v20 )
    v9 = (struct CWdsMetadataEntry *)*((_QWORD *)v18 + v5);
  else
    v15 = 1413;
  if ( ElValidateWin32(v15, v14, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x1C3u) )
  {
    Instance = v15 | 0x80070000;
    if ( !v15 )
      Instance = 0;
  }
  else
  {
    Instance = CWdsComMetadataEntry::CreateInstance(v9);
    if ( (int)ElValidateHr(Instance, v16, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x1C6u) >= 0 )
      *a4 = 0;
  }
LABEL_19:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( v4 )
    operator delete(v4);
  return Instance;
}

```

## disassembly

```asm
0x18000e8f0  mov     [rsp-28h+arg_8], rbx
0x18000e8f5  mov     [rsp-28h+arg_10], rsi
0x18000e8fa  mov     [rsp-28h+arg_18], rdi
0x18000e8ff  push    rbp
0x18000e900  push    r12
0x18000e902  push    r13
0x18000e904  push    r14
0x18000e906  push    r15
0x18000e908  mov     rbp, rsp
0x18000e90b  sub     rsp, 40h
0x18000e90f  xor     edi, edi
0x18000e911  mov     r14d, r8d
0x18000e914  and     [rbp+var_18], edi
0x18000e917  mov     r13, rcx
0x18000e91a  and     [rbp+var_14], edi
0x18000e91d  add     rcx, 88h; lpCriticalSection
0x18000e924  and     [rbp+arg_0], rdi
0x18000e928  mov     r15, r9
0x18000e92b  mov     [rbp+var_20], rdi
0x18000e92f  mov     rsi, rdx
0x18000e932  xor     r12d, r12d
0x18000e935  call    cs:__imp_EnterCriticalSection
0x18000e93b  mov     rcx, rsi; pbstr
0x18000e93e  call    ValidateNonEmptyBstr
0x18000e943  mov     ecx, 80070057h; int
0x18000e948  test    eax, eax
0x18000e94a  jz      short loc_18000E951
0x18000e94c  test    r15, r15
0x18000e94f  jnz     short loc_18000E96D
0x18000e951  mov     r9d, 1B6h; unsigned int
0x18000e957  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e95e  mov     ebx, ecx
0x18000e960  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e965  test    eax, eax
0x18000e967  js      loc_18000EA50
0x18000e96d  lea     rcx, [r13+40h]
0x18000e971  mov     rdx, rsi
0x18000e974  lea     r8, [rbp+var_20]
0x18000e978  call    ?GetInstancesOfTag@CWdsMetadata@@QEBAKPEBGPEAV?$CDynArray@PEBVCWdsMetadataEntry@@VCDeallocateNone@@@@@Z; CWdsMetadata::GetInstancesOfTag(ushort const *,CDynArray<CWdsMetadataEntry const *,CDeallocateNone> *)
0x18000e97d  mov     r9d, 1BAh; unsigned int
0x18000e983  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e98a  mov     ecx, eax; unsigned int
0x18000e98c  mov     edi, eax
0x18000e98e  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e993  test    eax, eax
0x18000e995  jz      short loc_18000E9AE
0x18000e997  movzx   ebx, di
0x18000e99a  or      ebx, 80070000h
0x18000e9a0  test    edi, edi
0x18000e9a2  cmovle  ebx, edi
0x18000e9a5  mov     rdi, [rbp+var_20]
0x18000e9a9  jmp     loc_18000EA50
0x18000e9ae  cmp     r14d, [rbp+var_14]
0x18000e9b2  jb      short loc_18000E9D1
0x18000e9b4  mov     ecx, 80070057h; int
0x18000e9b9  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e9c0  mov     r9d, 1BFh; unsigned int
0x18000e9c6  mov     ebx, ecx
0x18000e9c8  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e9cd  test    eax, eax
0x18000e9cf  js      short loc_18000E9A5
0x18000e9d1  mov     rdi, [rbp+var_20]
0x18000e9d5  xor     esi, esi
0x18000e9d7  cmp     r14d, [rbp+var_14]
0x18000e9db  jb      short loc_18000E9E4
0x18000e9dd  mov     esi, 585h
0x18000e9e2  jmp     short loc_18000E9E8
0x18000e9e4  mov     r12, [rdi+r14*8]
0x18000e9e8  mov     r9d, 1C3h; unsigned int
0x18000e9ee  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e9f5  mov     ecx, esi; unsigned int
0x18000e9f7  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000e9fc  test    eax, eax
0x18000e9fe  jz      short loc_18000EA0F
0x18000ea00  mov     ebx, esi
0x18000ea02  or      ebx, 80070000h
0x18000ea08  test    esi, esi
0x18000ea0a  cmovz   ebx, esi
0x18000ea0d  jmp     short loc_18000EA50
0x18000ea0f  lea     rdx, [rbp+arg_0]
0x18000ea13  mov     rcx, r12; struct CWdsMetadataEntry *
0x18000ea16  call    ?CreateInstance@CWdsComMetadataEntry@@SAJPEBVCWdsMetadataEntry@@PEAPEAV?$CComObject@VCWdsComMetadataEntry@@@ATL@@@Z; CWdsComMetadataEntry::CreateInstance(CWdsMetadataEntry const *,ATL::CComObject<CWdsComMetadataEntry> * *)
0x18000ea1b  mov     r9d, 1C6h; unsigned int
0x18000ea21  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000ea28  mov     ecx, eax; int
0x18000ea2a  mov     ebx, eax
0x18000ea2c  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000ea31  mov     rcx, [rbp+arg_0]
0x18000ea35  test    eax, eax
0x18000ea37  js      short loc_18000EA3E
0x18000ea39  mov     [r15], rcx
0x18000ea3c  xor     ecx, ecx
0x18000ea3e  test    rcx, rcx
0x18000ea41  jz      short loc_18000EA50
0x18000ea43  mov     rax, [rcx]
0x18000ea46  mov     rax, [rax+10h]
0x18000ea4a  call    cs:__guard_dispatch_icall_fptr
0x18000ea50  lea     rcx, [r13+88h]; lpCriticalSection
0x18000ea57  call    cs:__imp_LeaveCriticalSection
0x18000ea5d  test    rdi, rdi
0x18000ea60  jz      short loc_18000EA6A
0x18000ea62  mov     rcx, rdi; Block
0x18000ea65  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ea6a  lea     r11, [rsp+40h+var_s0]
0x18000ea6f  mov     eax, ebx
0x18000ea71  mov     rbx, [r11+38h]
0x18000ea75  mov     rsi, [r11+40h]
0x18000ea79  mov     rdi, [r11+48h]
0x18000ea7d  mov     rsp, r11
0x18000ea80  pop     r15
0x18000ea82  pop     r14
0x18000ea84  pop     r13
0x18000ea86  pop     r12
0x18000ea88  pop     rbp
0x18000ea89  retn
```
