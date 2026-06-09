# TimerBrokerHelper::Remove(_GUID,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180037f78`
- end: `0x1800380e3`
- name: `?Remove@TimerBrokerHelper@@QEAAJU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `363`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18008ef00`
- `0x18008f220`
- `0x1800a7538`
- `0x1800d7f04`

## callees

- `0x1800372d0`
- `0x180037f78`
- `0x180039448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037ffe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037ffe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037f9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180037f9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800380bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800380bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800380c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800380c9`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180038069`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180038069`
- `OLEAUT32!__imp_SysFreeString` at `0x1800380ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800380ae`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18003803d`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDeleteEvent` at `0x18003803d`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x180038016`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x180038016`

## string_xrefs

- `0x180038028`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\timerbrokerhelper.cpp`
- `0x18003804f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\timerbrokerhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall TimerBrokerHelper::Remove(__int64 a1, BSTR *a2, __int64 a3)
{
  BSTR *v6; // rbx
  int v7; // esi
  BSTR *i; // rax
  __int64 v9; // rcx
  BSTR v10; // rcx
  BSTR *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  int v15; // eax
  BSTR v16; // rcx
  BSTR *v17; // rdi
  HANDLE ProcessHeap; // rax
  int v20; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v6 = 0;
  v7 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 40));
  for ( i = *(BSTR **)(a1 + 24); i != (BSTR *)(a1 + 24); i = (BSTR *)*i )
  {
    v6 = i;
    v9 = (char *)*a2 - (char *)i[6];
    if ( *a2 == i[6] )
      v9 = (char *)a2[1] - (char *)i[7];
    if ( !v9 )
    {
      v10 = *i;
      if ( *((BSTR **)*i + 1) != i || (v11 = (BSTR *)i[1], *v11 != (BSTR)i) )
        __fastfail(3u);
      v7 = 1;
      *v11 = v10;
      *((_QWORD *)v10 + 1) = v11;
      break;
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 40));
  if ( v7 )
  {
    LOBYTE(v13) = 1;
    LOBYTE(v12) = 1;
    v14 = BiPtDisassociateWorkItemEx(v6 + 4, v12, v13);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x1EF,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\timerbrokerhelper.cpp",
        (const char *)(unsigned int)v14,
        v20);
    v15 = BiPtDeleteEvent(v6 + 8);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_NtStatus(
        retaddr,
        (void *)0x1F0,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\timerbrokerhelper.cpp",
        (const char *)(unsigned int)v15,
        v20);
    v16 = v6[3];
    if ( v16 )
      RtlUnsubscribeWnfNotificationWaitForCompletion(v16);
    v6[3] = 0;
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 16));
    v17 = v6 + 47;
    std::wstring::assign(a3, v6[47]);
    if ( *v17 )
    {
      SysFreeString(*v17);
      *v17 = 0;
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180037f78  mov     [rsp+arg_8], rbx
0x180037f7d  push    rsi
0x180037f7e  push    rdi
0x180037f7f  push    r12
0x180037f81  push    r14
0x180037f83  push    r15; int
0x180037f85  sub     rsp, 20h
0x180037f89  mov     r12, r8
0x180037f8c  mov     r14, rdx
0x180037f8f  mov     rdi, rcx
0x180037f92  xor     ebx, ebx
0x180037f94  mov     [rsp+48h+arg_0], rbx
0x180037f99  xor     esi, esi
0x180037f9b  add     rcx, 28h ; '('; SRWLock
0x180037f9f  call    cs:__imp_AcquireSRWLockExclusive
0x180037fa5  lea     r9, [rdi+18h]
0x180037fa9  mov     rax, [r9]
0x180037fac  cmp     rax, r9
0x180037faf  jz      short loc_180037FFA
0x180037fb1  mov     rbx, rax
0x180037fb4  mov     [rsp+48h+arg_0], rax
0x180037fb9  mov     rcx, [r14]
0x180037fbc  sub     rcx, [rax+30h]
0x180037fc0  jnz     short loc_180037FCA
0x180037fc2  mov     rcx, [r14+8]
0x180037fc6  sub     rcx, [rax+38h]
0x180037fca  test    rcx, rcx
0x180037fcd  jz      short loc_180037FD4
0x180037fcf  mov     rax, [rax]
0x180037fd2  jmp     short loc_180037FAC
0x180037fd4  mov     rcx, [rax]
0x180037fd7  cmp     [rcx+8], rax
0x180037fdb  jnz     loc_180038095
0x180037fe1  mov     rdx, [rax+8]
0x180037fe5  cmp     [rdx], rax
0x180037fe8  jnz     loc_180038095
0x180037fee  mov     esi, 1
0x180037ff3  mov     [rdx], rcx
0x180037ff6  mov     [rcx+8], rdx
0x180037ffa  lea     rcx, [rdi+28h]; SRWLock
0x180037ffe  call    cs:__imp_ReleaseSRWLockExclusive
0x180038004  test    esi, esi
0x180038006  jz      loc_1800380CF
0x18003800c  lea     rcx, [rbx+20h]
0x180038010  mov     r8b, 1
0x180038013  mov     dl, r8b
0x180038016  call    cs:__imp_BiPtDisassociateWorkItemEx
0x18003801c  mov     rcx, [rsp+48h]; this
0x180038021  test    eax, eax
0x180038023  jns     short loc_180038039
0x180038025  mov     r9d, eax; char *
0x180038028  lea     r8, aOnecoreuapBase_155; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003802f  mov     edx, 1EFh; void *
0x180038034  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180038039  lea     rcx, [rbx+40h]
0x18003803d  call    cs:__imp_BiPtDeleteEvent
0x180038043  mov     rcx, [rsp+48h]; this
0x180038048  test    eax, eax
0x18003804a  jns     short loc_180038060
0x18003804c  mov     r9d, eax; char *
0x18003804f  lea     r8, aOnecoreuapBase_155; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180038056  mov     edx, 1F0h; void *
0x18003805b  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180038060  mov     rcx, [rbx+18h]
0x180038064  test    rcx, rcx
0x180038067  jz      short loc_18003806F
0x180038069  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18003806f  mov     qword ptr [rbx+18h], 0
0x180038077  lock dec dword ptr [rdi+10h]
0x18003807b  lea     rdi, [rbx+178h]
0x180038082  mov     [rsp+48h+arg_18], rdi
0x180038087  mov     rdx, [rdi]
0x18003808a  mov     rcx, r12
0x18003808d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180038092  nop
0x180038093  jmp     short loc_1800380A6
0x180038095  mov     ecx, 3
0x18003809a  int     29h; Win8: RtlFailFast(ecx)
0x18003809c  mov     rbx, [rsp+48h+arg_0]
0x1800380a1  mov     rdi, [rsp+48h+arg_18]
0x1800380a6  mov     rcx, [rdi]; bstrString
0x1800380a9  test    rcx, rcx
0x1800380ac  jz      short loc_1800380BB
0x1800380ae  call    cs:__imp_SysFreeString
0x1800380b4  mov     qword ptr [rdi], 0
0x1800380bb  call    cs:__imp_GetProcessHeap
0x1800380c1  mov     rcx, rax; hHeap
0x1800380c4  mov     r8, rbx; lpMem
0x1800380c7  xor     edx, edx; dwFlags
0x1800380c9  call    cs:__imp_HeapFree
0x1800380cf  xor     eax, eax
0x1800380d1  mov     rbx, [rsp+48h+arg_8]
0x1800380d6  add     rsp, 20h
0x1800380da  pop     r15
0x1800380dc  pop     r14
0x1800380de  pop     r12
0x1800380e0  pop     rdi
0x1800380e1  pop     rsi
0x1800380e2  retn
```
