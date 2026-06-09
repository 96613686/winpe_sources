# CBandwidthManager::UpdateMulticastSessionGroups(CBandwidthManager::Interface *)

- ea: `0x18001853c`
- end: `0x18001869a`
- name: `?UpdateMulticastSessionGroups@CBandwidthManager@@AEAAXPEAUInterface@1@@Z`
- size: `350`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct CBandwidthManager::Interface *)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180018174`
- `0x1800186a0`
- `0x180018988`

## callees

- `0x18001853c`
- `0x180019ea0`
- `0x180024228`
- `0x180026670`
- `0x180026d70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180018580`
- `KERNEL32!LeaveCriticalSection` at `0x18001859d`
- `KERNEL32!LeaveCriticalSection` at `0x18001862d`
- `KERNEL32!LeaveCriticalSection` at `0x18001866d`
- `KERNEL32!LeaveCriticalSection` at `0x180018580`
- `KERNEL32!LeaveCriticalSection` at `0x18001859d`
- `KERNEL32!LeaveCriticalSection` at `0x18001862d`
- `KERNEL32!LeaveCriticalSection` at `0x18001866d`
- `KERNEL32!EnterCriticalSection` at `0x180018567`
- `KERNEL32!EnterCriticalSection` at `0x180018574`
- `KERNEL32!EnterCriticalSection` at `0x180018591`
- `KERNEL32!EnterCriticalSection` at `0x180018621`
- `KERNEL32!EnterCriticalSection` at `0x180018567`
- `KERNEL32!EnterCriticalSection` at `0x180018574`
- `KERNEL32!EnterCriticalSection` at `0x180018591`
- `KERNEL32!EnterCriticalSection` at `0x180018621`

## pseudocode

```c
void __fastcall CBandwidthManager::UpdateMulticastSessionGroups(
        LPCRITICAL_SECTION lpCriticalSection,
        struct CBandwidthManager::Interface *a2)
{
  int v4; // ebx
  unsigned __int64 v5; // rbx
  unsigned __int64 DebugInfo_low; // rsi
  unsigned __int16 *v7; // rdi
  unsigned int v8; // ebx
  __int64 v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  unsigned __int16 v11[70]; // [rsp+34h] [rbp-C4h] BYREF

  EnterCriticalSection(lpCriticalSection);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 56));
  v4 = *((_DWORD *)a2 + 12);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 56));
  if ( v4 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 56));
    v5 = *((unsigned int *)a2 + 12);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 56));
    DebugInfo_low = *((_QWORD *)a2 + 3) * (unsigned __int64)HIDWORD(lpCriticalSection[1].SpinCount) / 0x64 / v5;
    if ( LODWORD(lpCriticalSection[3].DebugInfo)
      && *((_QWORD *)a2 + 3) * (unsigned __int64)HIDWORD(lpCriticalSection[1].SpinCount) / 0x64 / v5 >= LODWORD(lpCriticalSection[3].DebugInfo) )
    {
      DebugInfo_low = LODWORD(lpCriticalSection[3].DebugInfo);
    }
    if ( g_ErrLibTraceFunction )
    {
      v7 = v11;
      if ( HexToString((const unsigned __int8 *)a2, *((unsigned int *)a2 + 4), v11, 0x40u) )
        v7 = L"<<Failed>>";
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 56));
      v8 = *((_DWORD *)a2 + 12);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 56));
      g_ErrLibTraceFunction(
        L"[Bandwidth] Allocating %I64uBps to each session (Total %u sessions) on NIC %s.",
        DebugInfo_low,
        v8,
        v7);
    }
    v9 = *((_QWORD *)a2 + 4);
    while ( v9 )
    {
      v10 = *(struct _RTL_CRITICAL_SECTION **)v9;
      v9 = *(_QWORD *)(v9 + 16);
      CMulticastSessionGroup::UpdateBandwidth(v10, (struct _RTL_CRITICAL_SECTION_DEBUG *)DebugInfo_low);
    }
  }
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001853c  mov     [rsp+arg_10], rbx
0x180018541  push    rbp
0x180018542  push    rsi
0x180018543  push    rdi
0x180018544  push    r14
0x180018546  push    r15
0x180018548  sub     rsp, 0D0h
0x18001854f  mov     rax, cs:__security_cookie
0x180018556  xor     rax, rsp
0x180018559  mov     [rsp+0F8h+var_38], rax
0x180018561  mov     rbp, rdx
0x180018564  mov     r15, rcx
0x180018567  call    cs:__imp_EnterCriticalSection
0x18001856d  lea     r14, [rbp+38h]
0x180018571  mov     rcx, r14; lpCriticalSection
0x180018574  call    cs:__imp_EnterCriticalSection
0x18001857a  mov     ebx, [rbp+30h]
0x18001857d  mov     rcx, r14; lpCriticalSection
0x180018580  call    cs:__imp_LeaveCriticalSection
0x180018586  test    ebx, ebx
0x180018588  jz      loc_18001866A
0x18001858e  mov     rcx, r14; lpCriticalSection
0x180018591  call    cs:__imp_EnterCriticalSection
0x180018597  mov     ebx, [rbp+30h]
0x18001859a  mov     rcx, r14; lpCriticalSection
0x18001859d  call    cs:__imp_LeaveCriticalSection
0x1800185a3  mov     r8d, [r15+4Ch]
0x1800185a7  mov     rax, 47AE147AE147AE15h
0x1800185b1  imul    r8, [rbp+18h]
0x1800185b6  mul     r8
0x1800185b9  sub     r8, rdx
0x1800185bc  shr     r8, 1
0x1800185bf  lea     rax, [rdx+r8]
0x1800185c3  xor     edx, edx
0x1800185c5  shr     rax, 6
0x1800185c9  div     rbx
0x1800185cc  cmp     dword ptr [r15+78h], 0
0x1800185d1  mov     rsi, rax
0x1800185d4  jbe     short loc_1800185E1
0x1800185d6  mov     ecx, [r15+78h]
0x1800185da  cmp     rax, rcx
0x1800185dd  cmovnb  rsi, rcx
0x1800185e1  cmp     cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA, 0; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x1800185e9  jz      short loc_180018650
0x1800185eb  mov     edx, [rbp+10h]; unsigned __int64
0x1800185ee  lea     r8, [rsp+0F8h+var_C4]; unsigned __int16 *
0x1800185f3  mov     r9d, 40h ; '@'; unsigned __int64
0x1800185f9  mov     rcx, rbp; unsigned __int8 *
0x1800185fc  call    ?HexToString@@YAKPEBE_KPEAG1@Z; HexToString(uchar const *,unsigned __int64,ushort *,unsigned __int64)
0x180018601  xor     ecx, ecx
0x180018603  lea     rdi, [rsp+0F8h+var_C4]
0x180018608  test    eax, eax
0x18001860a  setnz   cl
0x18001860d  test    eax, eax
0x18001860f  mov     [rsp+0F8h+var_C8], ecx
0x180018613  lea     rcx, aFailed; "<<Failed>>"
0x18001861a  cmovnz  rdi, rcx
0x18001861e  mov     rcx, r14; lpCriticalSection
0x180018621  call    cs:__imp_EnterCriticalSection
0x180018627  mov     ebx, [rbp+30h]
0x18001862a  mov     rcx, r14; lpCriticalSection
0x18001862d  call    cs:__imp_LeaveCriticalSection
0x180018633  mov     rax, cs:?g_ErrLibTraceFunction@@3P6AXPEBGZZEA; void (*g_ErrLibTraceFunction)(ushort const *,...)
0x18001863a  lea     rcx, aBandwidthAlloc; "[Bandwidth] Allocating %I64uBps to each"...
0x180018641  mov     r9, rdi
0x180018644  mov     r8d, ebx
0x180018647  mov     rdx, rsi
0x18001864a  call    cs:__guard_dispatch_icall_fptr
0x180018650  mov     rbx, [rbp+20h]
0x180018654  jmp     short loc_180018665
0x180018656  mov     rcx, [rbx]; this
0x180018659  mov     rdx, rsi; unsigned __int64
0x18001865c  mov     rbx, [rbx+10h]
0x180018660  call    ?UpdateBandwidth@CMulticastSessionGroup@@QEAAX_K@Z; CMulticastSessionGroup::UpdateBandwidth(unsigned __int64)
0x180018665  test    rbx, rbx
0x180018668  jnz     short loc_180018656
0x18001866a  mov     rcx, r15; lpCriticalSection
0x18001866d  call    cs:__imp_LeaveCriticalSection
0x180018673  mov     rcx, [rsp+0F8h+var_38]
0x18001867b  xor     rcx, rsp; StackCookie
0x18001867e  call    __security_check_cookie
0x180018683  mov     rbx, [rsp+0F8h+arg_10]
0x18001868b  add     rsp, 0D0h
0x180018692  pop     r15
0x180018694  pop     r14
0x180018696  pop     rdi
0x180018697  pop     rsi
0x180018698  pop     rbp
0x180018699  retn
```
