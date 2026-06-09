# CWdsComMetadataBuilder::AppendVersionEntry(ushort *,unsigned __int64)

- ea: `0x18000f650`
- end: `0x18000f70a`
- name: `?AppendVersionEntry@CWdsComMetadataBuilder@@UEAAJPEAG_K@Z`
- size: `186`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000c03c`
- `0x18000e3e4`
- `0x18000f650`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f67e`
- `KERNEL32!EnterCriticalSection` at `0x18000f67e`
- `KERNEL32!LeaveCriticalSection` at `0x18000f6e7`
- `KERNEL32!LeaveCriticalSection` at `0x18000f6e7`

## string_xrefs

- `0x18000f695`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f6c2`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendVersionEntry(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        union _ULARGE_INTEGER a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdx
  signed int appended; // edi
  const char *v10; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (unsigned int)ValidateNonEmptyBstr(a2)
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x436u) >= 0) )
  {
    appended = CWdsMetadata::AppendVersionEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2, a3);
    if ( ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x43Cu) )
    {
      v7 = (unsigned __int16)appended | 0x80070000;
      if ( appended <= 0 )
        v7 = appended;
    }
  }
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000f650  mov     rax, rsp
0x18000f653  mov     [rax+8], rbx
0x18000f657  mov     [rax+10h], rbp
0x18000f65b  mov     [rax+18h], rsi
0x18000f65f  mov     [rax+20h], rdi
0x18000f663  push    r14
0x18000f665  sub     rsp, 20h
0x18000f669  lea     rsi, [rcx+88h]
0x18000f670  mov     rbp, rcx
0x18000f673  mov     rcx, rsi; lpCriticalSection
0x18000f676  mov     r14, r8
0x18000f679  mov     rdi, rdx
0x18000f67c  xor     ebx, ebx
0x18000f67e  call    cs:__imp_EnterCriticalSection
0x18000f684  mov     rcx, rdi; pbstr
0x18000f687  call    ValidateNonEmptyBstr
0x18000f68c  test    eax, eax
0x18000f68e  jnz     short loc_18000F6AD
0x18000f690  mov     ebx, 80070057h
0x18000f695  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f69c  mov     ecx, ebx; int
0x18000f69e  mov     r9d, 436h; unsigned int
0x18000f6a4  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f6a9  test    eax, eax
0x18000f6ab  js      short loc_18000F6E4
0x18000f6ad  lea     rcx, [rbp+40h]; this
0x18000f6b1  mov     r8, r14; union _ULARGE_INTEGER
0x18000f6b4  mov     rdx, rdi; unsigned __int16 *
0x18000f6b7  call    ?AppendVersionEntry@CWdsMetadata@@QEAAKPEBGT_ULARGE_INTEGER@@@Z; CWdsMetadata::AppendVersionEntry(ushort const *,_ULARGE_INTEGER)
0x18000f6bc  mov     r9d, 43Ch; unsigned int
0x18000f6c2  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f6c9  mov     ecx, eax; unsigned int
0x18000f6cb  mov     edi, eax
0x18000f6cd  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f6d2  test    eax, eax
0x18000f6d4  jz      short loc_18000F6E4
0x18000f6d6  movzx   ebx, di
0x18000f6d9  or      ebx, 80070000h
0x18000f6df  test    edi, edi
0x18000f6e1  cmovle  ebx, edi
0x18000f6e4  mov     rcx, rsi; lpCriticalSection
0x18000f6e7  call    cs:__imp_LeaveCriticalSection
0x18000f6ed  mov     rbp, [rsp+28h+arg_8]
0x18000f6f2  mov     eax, ebx
0x18000f6f4  mov     rbx, [rsp+28h+arg_0]
0x18000f6f9  mov     rsi, [rsp+28h+arg_10]
0x18000f6fe  mov     rdi, [rsp+28h+arg_18]
0x18000f703  add     rsp, 20h
0x18000f707  pop     r14
0x18000f709  retn
```
