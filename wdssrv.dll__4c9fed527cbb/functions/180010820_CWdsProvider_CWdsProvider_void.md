# CWdsProvider::~CWdsProvider(void)

- ea: `0x180010820`
- end: `0x1800108cc`
- name: `??1CWdsProvider@@UEAA@XZ`
- size: `172`
- prototype: `void __fastcall(CWdsProvider *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800108e0`

## callees

- `0x180010820`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800108af`
- `KERNEL32!DeleteCriticalSection` at `0x1800108af`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180010897`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x180010897`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010882`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180010882`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18001085a`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x18001085a`

## string_xrefs

- `0x18001086f`: `[%s] Deleted.`

## pseudocode

```c
void __fastcall CWdsProvider::~CWdsProvider(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWdsProvider::`vftable';
  if ( LODWORD(this[6].OwningThread) )
    WdsAssert("base\\eco\\wds\\wdssrv\\server\\src\\wdsprovider.cpp", 0x27u, "m_uAllocCount == 0", 1, 0);
  if ( this->OwningThread )
  {
    CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[%s] Deleted.");
    OwningThread = this->OwningThread;
    if ( OwningThread )
    {
      WdsPrivateHpFree(OwningThread);
      this->OwningThread = 0;
    }
  }
  DeleteCriticalSection(this + 5);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CRefCount::`vftable';
}

```

## disassembly

```asm
0x180010820  push    rbx
0x180010822  sub     rsp, 30h
0x180010826  lea     rax, ??_7CWdsProvider@@6B@; const CWdsProvider::`vftable'
0x18001082d  mov     rbx, rcx
0x180010830  mov     [rcx], rax
0x180010833  mov     eax, [rcx+100h]
0x180010839  test    eax, eax
0x18001083b  jz      short loc_180010866
0x18001083d  and     [rsp+38h+var_18], 0
0x180010842  lea     r8, aMUalloccount0; "m_uAllocCount == 0"
0x180010849  mov     r9d, 1
0x18001084f  lea     rcx, aBaseEcoWdsWdss_11; "base\\eco\\wds\\wdssrv\\server\\src\\wd"...
0x180010856  lea     edx, [r9+26h]
0x18001085a  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180010861  nop     dword ptr [rax+rax+00h]
0x180010866  mov     r9, [rbx+10h]
0x18001086a  test    r9, r9
0x18001086d  jz      short loc_1800108A8
0x18001086f  lea     r8, aSDeleted; "[%s] Deleted."
0x180010876  mov     edx, 20000h
0x18001087b  lea     rcx, qword_180039310
0x180010882  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180010889  nop     dword ptr [rax+rax+00h]
0x18001088e  mov     rcx, [rbx+10h]
0x180010892  test    rcx, rcx
0x180010895  jz      short loc_1800108A8
0x180010897  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18001089e  nop     dword ptr [rax+rax+00h]
0x1800108a3  and     qword ptr [rbx+10h], 0
0x1800108a8  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800108af  call    cs:__imp_DeleteCriticalSection
0x1800108b6  nop     dword ptr [rax+rax+00h]
0x1800108bb  lea     rax, ??_7CRefCount@@6B@; const CRefCount::`vftable'
0x1800108c2  mov     [rbx], rax
0x1800108c5  add     rsp, 30h
0x1800108c9  pop     rbx
0x1800108ca  retn
```
