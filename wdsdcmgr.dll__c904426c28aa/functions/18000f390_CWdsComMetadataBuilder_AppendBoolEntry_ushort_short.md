# CWdsComMetadataBuilder::AppendBoolEntry(ushort *,short)

- ea: `0x18000f390`
- end: `0x18000f45c`
- name: `?AppendBoolEntry@CWdsComMetadataBuilder@@UEAAJPEAGF@Z`
- size: `204`
- prototype: `int(CWdsComMetadataBuilder *__hidden this, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000bd00`
- `0x18000e3e4`
- `0x18000f390`
- `0x180014d58`
- `0x180014ee0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18000f3bf`
- `KERNEL32!EnterCriticalSection` at `0x18000f3bf`
- `KERNEL32!LeaveCriticalSection` at `0x18000f439`
- `KERNEL32!LeaveCriticalSection` at `0x18000f439`

## string_xrefs

- `0x18000f3df`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`
- `0x18000f414`: `base\eco\wds\lib\metadata\com\wdscommetadatabuilder.cpp`

## pseudocode

```c
__int64 __fastcall CWdsComMetadataBuilder::AppendBoolEntry(
        CWdsComMetadataBuilder *this,
        unsigned __int16 *a2,
        __int16 a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  unsigned int v7; // ebx
  const char *v8; // rdx
  signed int appended; // edi
  const char *v10; // rdx

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  if ( (unsigned int)ValidateNonEmptyBstr(a2) && (unsigned __int16)(a3 + 1) <= 1u
    || (v7 = -2147024809,
        (int)ElValidateHr(-2147024809, v8, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x3ABu) >= 0) )
  {
    appended = CWdsMetadata::AppendBoolEntry((CWdsComMetadataBuilder *)((char *)this + 64), a2, a3 == -1);
    if ( ElValidateWin32(appended, v10, "base\\eco\\wds\\lib\\metadata\\com\\wdscommetadatabuilder.cpp", 0x3B0u) )
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
0x18000f390  mov     rax, rsp
0x18000f393  mov     [rax+8], rbx
0x18000f397  mov     [rax+10h], rbp
0x18000f39b  mov     [rax+18h], rsi
0x18000f39f  mov     [rax+20h], rdi
0x18000f3a3  push    r14
0x18000f3a5  sub     rsp, 20h
0x18000f3a9  lea     rsi, [rcx+88h]
0x18000f3b0  mov     r14, rcx
0x18000f3b3  mov     rcx, rsi; lpCriticalSection
0x18000f3b6  movzx   edi, r8w
0x18000f3ba  mov     rbp, rdx
0x18000f3bd  xor     ebx, ebx
0x18000f3bf  call    cs:__imp_EnterCriticalSection
0x18000f3c5  mov     rcx, rbp; pbstr
0x18000f3c8  call    ValidateNonEmptyBstr
0x18000f3cd  test    eax, eax
0x18000f3cf  jz      short loc_18000F3DA
0x18000f3d1  lea     eax, [rdi+1]
0x18000f3d4  cmp     ax, 1
0x18000f3d8  jbe     short loc_18000F3F7
0x18000f3da  mov     ebx, 80070057h
0x18000f3df  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f3e6  mov     ecx, ebx; int
0x18000f3e8  mov     r9d, 3ABh; unsigned int
0x18000f3ee  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x18000f3f3  test    eax, eax
0x18000f3f5  js      short loc_18000F436
0x18000f3f7  xor     r8d, r8d
0x18000f3fa  lea     rcx, [r14+40h]; this
0x18000f3fe  cmp     di, 0FFFFh
0x18000f402  mov     rdx, rbp; unsigned __int16 *
0x18000f405  setz    r8b; int
0x18000f409  call    ?AppendBoolEntry@CWdsMetadata@@QEAAKPEBGH@Z; CWdsMetadata::AppendBoolEntry(ushort const *,int)
0x18000f40e  mov     r9d, 3B0h; unsigned int
0x18000f414  lea     r8, aBaseEcoWdsLibM_0; "base\\eco\\wds\\lib\\metadata\\com\\wds"...
0x18000f41b  mov     ecx, eax; unsigned int
0x18000f41d  mov     edi, eax
0x18000f41f  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18000f424  test    eax, eax
0x18000f426  jz      short loc_18000F436
0x18000f428  movzx   ebx, di
0x18000f42b  or      ebx, 80070000h
0x18000f431  test    edi, edi
0x18000f433  cmovle  ebx, edi
0x18000f436  mov     rcx, rsi; lpCriticalSection
0x18000f439  call    cs:__imp_LeaveCriticalSection
0x18000f43f  mov     rbp, [rsp+28h+arg_8]
0x18000f444  mov     eax, ebx
0x18000f446  mov     rbx, [rsp+28h+arg_0]
0x18000f44b  mov     rsi, [rsp+28h+arg_10]
0x18000f450  mov     rdi, [rsp+28h+arg_18]
0x18000f455  add     rsp, 20h
0x18000f459  pop     r14
0x18000f45b  retn
```
