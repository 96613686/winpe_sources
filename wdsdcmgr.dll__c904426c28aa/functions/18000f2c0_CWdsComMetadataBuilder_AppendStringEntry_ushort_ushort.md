# CWdsComMetadataBuilder::AppendStringEntry(ushort *,ushort *)

- ea: `0x18000f2c0`
- end: `0x18000f386`
- name: `?AppendStringEntry@CWdsComMetadataBuilder@@UEAAJPEAG0@Z`
- size: `198`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000bb58`
- `0x18000e3e4`
- `0x18000f2c0`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f2ee`
- `KERNEL32!EnterCriticalSection` at `0x18000f2ee`
- `KERNEL32!LeaveCriticalSection` at `0x18000f363`
- `KERNEL32!LeaveCriticalSection` at `0x18000f363`

## string_xrefs

- `0x18000f311`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f33e`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendStringEntry(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdx
  signed int appended; // edi
  const char *v10; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && (unsigned int)ValidateNonEmptyBstr(a3)
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x37Fu) >= 0) )
  {
    appended = CWdsMetadata::AppendStringEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2, a3);
    if ( ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x383u) )
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
0x18000f2c0  mov     rax, rsp
0x18000f2c3  mov     [rax+8], rbx
0x18000f2c7  mov     [rax+10h], rbp
0x18000f2cb  mov     [rax+18h], rsi
0x18000f2cf  mov     [rax+20h], rdi
0x18000f2d3  push    r14
0x18000f2d5  sub     rsp, 20h
0x18000f2d9  lea     rsi, [rcx+88h]
0x18000f2e0  mov     r14, rcx
0x18000f2e3  mov     rcx, rsi; lpCriticalSection
0x18000f2e6  mov     rdi, r8
0x18000f2e9  mov     rbp, rdx
0x18000f2ec  xor     ebx, ebx
0x18000f2ee  call    cs:__imp_EnterCriticalSection
0x18000f2f4  mov     rcx, rbp; pbstr
0x18000f2f7  call    ValidateNonEmptyBstr
0x18000f2fc  test    eax, eax
0x18000f2fe  jz      short loc_18000F30C
0x18000f300  mov     rcx, rdi; pbstr
0x18000f303  call    ValidateNonEmptyBstr
0x18000f308  test    eax, eax
0x18000f30a  jnz     short loc_18000F329
0x18000f30c  mov     ebx, 80070057h
0x18000f311  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f318  mov     ecx, ebx; int
0x18000f31a  mov     r9d, 37Fh; unsigned int
0x18000f320  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f325  test    eax, eax
0x18000f327  js      short loc_18000F360
0x18000f329  lea     rcx, [r14+40h]; this
0x18000f32d  mov     r8, rdi; unsigned __int16 *
0x18000f330  mov     rdx, rbp; unsigned __int16 *
0x18000f333  call    ?AppendStringEntry@CWdsMetadata@@QEAAKPEBG0@Z; CWdsMetadata::AppendStringEntry(ushort const *,ushort const *)
0x18000f338  mov     r9d, 383h; unsigned int
0x18000f33e  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f345  mov     ecx, eax; unsigned int
0x18000f347  mov     edi, eax
0x18000f349  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f34e  test    eax, eax
0x18000f350  jz      short loc_18000F360
0x18000f352  movzx   ebx, di
0x18000f355  or      ebx, 80070000h
0x18000f35b  test    edi, edi
0x18000f35d  cmovle  ebx, edi
0x18000f360  mov     rcx, rsi; lpCriticalSection
0x18000f363  call    cs:__imp_LeaveCriticalSection
0x18000f369  mov     rbp, [rsp+28h+arg_8]
0x18000f36e  mov     eax, ebx
0x18000f370  mov     rbx, [rsp+28h+arg_0]
0x18000f375  mov     rsi, [rsp+28h+arg_10]
0x18000f37a  mov     rdi, [rsp+28h+arg_18]
0x18000f37f  add     rsp, 20h
0x18000f383  pop     r14
0x18000f385  retn
```
