# CWdsComMetadataBuilder::GetEntryCountByTag(ushort *,ulong *)

- ea: `0x18000e850`
- end: `0x18000e8e6`
- name: `?GetEntryCountByTag@CWdsComMetadataBuilder@@UEAAJPEAGPEAK@Z`
- size: `150`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000adf4`
- `0x18000e3e4`
- `0x18000e850`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000e87e`
- `KERNEL32!EnterCriticalSection` at `0x18000e87e`
- `KERNEL32!LeaveCriticalSection` at `0x18000e8c3`
- `KERNEL32!LeaveCriticalSection` at `0x18000e8c3`

## string_xrefs

- `0x18000e89a`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::GetEntryCountByTag(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && a3
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x183u) >= 0) )
  {
    *a3 = CWdsMetadata::CountInstancesOfTag((CWdsComMetadataBuilder *)((char *)this + 64), a2);
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000e850  mov     rax, rsp
0x18000e853  mov     [rax+8], rbx
0x18000e857  mov     [rax+10h], rbp
0x18000e85b  mov     [rax+18h], rsi
0x18000e85f  mov     [rax+20h], rdi
0x18000e863  push    r14
0x18000e865  sub     rsp, 20h
0x18000e869  lea     rsi, [rcx+88h]
0x18000e870  mov     r14, rcx
0x18000e873  mov     rcx, rsi; lpCriticalSection
0x18000e876  mov     rdi, r8
0x18000e879  mov     rbp, rdx
0x18000e87c  xor     ebx, ebx
0x18000e87e  call    cs:__imp_EnterCriticalSection
0x18000e884  mov     rcx, rbp; pbstr
0x18000e887  call    ValidateNonEmptyBstr
0x18000e88c  test    eax, eax
0x18000e88e  jz      short loc_18000E895
0x18000e890  test    rdi, rdi
0x18000e893  jnz     short loc_18000E8B2
0x18000e895  mov     ebx, 80070057h
0x18000e89a  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000e8a1  mov     ecx, ebx; int
0x18000e8a3  mov     r9d, 183h; unsigned int
0x18000e8a9  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000e8ae  test    eax, eax
0x18000e8b0  js      short loc_18000E8C0
0x18000e8b2  lea     rcx, [r14+40h]; this
0x18000e8b6  mov     rdx, rbp; unsigned __int16 *
0x18000e8b9  call    ?CountInstancesOfTag@CWdsMetadata@@QEBAKPEBG@Z; CWdsMetadata::CountInstancesOfTag(ushort const *)
0x18000e8be  mov     [rdi], eax
0x18000e8c0  mov     rcx, rsi; lpCriticalSection
0x18000e8c3  call    cs:__imp_LeaveCriticalSection
0x18000e8c9  mov     rbp, [rsp+28h+arg_8]
0x18000e8ce  mov     eax, ebx
0x18000e8d0  mov     rbx, [rsp+28h+arg_0]
0x18000e8d5  mov     rsi, [rsp+28h+arg_10]
0x18000e8da  mov     rdi, [rsp+28h+arg_18]
0x18000e8df  add     rsp, 20h
0x18000e8e3  pop     r14
0x18000e8e5  retn
```
