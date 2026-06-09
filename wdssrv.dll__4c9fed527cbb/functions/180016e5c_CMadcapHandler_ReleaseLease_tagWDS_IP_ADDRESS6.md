# CMadcapHandler::ReleaseLease(tagWDS_IP_ADDRESS6 *)

- ea: `0x180016e5c`
- end: `0x180016f8f`
- name: `?ReleaseLease@CMadcapHandler@@QEAAKPEAUtagWDS_IP_ADDRESS6@@@Z`
- size: `307`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct tagWDS_IP_ADDRESS6 *Buf2)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001a474`

## callees

- `0x180016e5c`
- `0x18001c106`

## import_xrefs

- `msvcrt!time` at `0x180016f51`
- `msvcrt!time` at `0x180016f51`
- `KERNEL32!LeaveCriticalSection` at `0x180016eda`
- `KERNEL32!LeaveCriticalSection` at `0x180016f67`
- `KERNEL32!LeaveCriticalSection` at `0x180016eda`
- `KERNEL32!LeaveCriticalSection` at `0x180016f67`
- `KERNEL32!EnterCriticalSection` at `0x180016e7a`
- `KERNEL32!EnterCriticalSection` at `0x180016e8d`
- `KERNEL32!EnterCriticalSection` at `0x180016e7a`
- `KERNEL32!EnterCriticalSection` at `0x180016e8d`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016f0a`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180016f0a`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180016f3d`
- `WdsServerCommonLib!?WdsAssert@@YAXPEBDK0HH@Z` at `0x180016f3d`

## string_xrefs

- `0x180016ef7`: `[MADCAP] Lease added back to cache: %s`

## pseudocode

```c
__int64 __fastcall CMadcapHandler::ReleaseLease(LPCRITICAL_SECTION lpCriticalSection, struct tagWDS_IP_ADDRESS6 *Buf2)
{
  unsigned int v4; // ebx
  _QWORD *v5; // rdi
  _QWORD *OwningThread; // rsi
  size_t v7; // r14

  EnterCriticalSection(lpCriticalSection);
  v4 = 0;
  v5 = 0;
  EnterCriticalSection(lpCriticalSection);
  OwningThread = lpCriticalSection[1].OwningThread;
  if ( OwningThread )
  {
    v7 = *((unsigned int *)Buf2 + 4);
    do
    {
      v5 = OwningThread;
      OwningThread = (_QWORD *)OwningThread[29];
      if ( *((_DWORD *)v5 + 48) == (_DWORD)v7 && !memcmp_0(v5 + 22, Buf2, v7) )
        break;
      v5 = 0;
    }
    while ( OwningThread );
  }
  LeaveCriticalSection(lpCriticalSection);
  if ( v5 )
  {
    CTrace::Trace((CTrace *)qword_180039310, 0x20000u, L"[MADCAP] Lease added back to cache: %s", v5[25]);
    if ( *((_DWORD *)v5 + 52) )
      WdsAssert("base\\eco\\wds\\wdssrv\\server\\src\\madcaphandler.cpp", 0x45Cu, "pLease->m_bAvailable == 0", 1, 0);
    *((_DWORD *)v5 + 52) = 1;
    v5[27] = time(0);
  }
  else
  {
    v4 = 2;
  }
  LeaveCriticalSection(lpCriticalSection);
  return v4;
}

```

## disassembly

```asm
0x180016e5c  mov     [rsp+arg_0], rbx
0x180016e61  mov     [rsp+arg_8], rbp
0x180016e66  mov     [rsp+arg_10], rsi
0x180016e6b  push    rdi
0x180016e6c  push    r14
0x180016e6e  push    r15
0x180016e70  sub     rsp, 30h
0x180016e74  mov     r15, rdx
0x180016e77  mov     rbp, rcx
0x180016e7a  call    cs:__imp_EnterCriticalSection
0x180016e81  nop     dword ptr [rax+rax+00h]
0x180016e86  xor     ebx, ebx
0x180016e88  mov     rcx, rbp; lpCriticalSection
0x180016e8b  mov     edi, ebx
0x180016e8d  call    cs:__imp_EnterCriticalSection
0x180016e94  nop     dword ptr [rax+rax+00h]
0x180016e99  mov     rsi, [rbp+38h]
0x180016e9d  test    rsi, rsi
0x180016ea0  jz      short loc_180016ED7
0x180016ea2  mov     r14d, [r15+10h]
0x180016ea6  mov     rdi, rsi
0x180016ea9  mov     rsi, [rsi+0E8h]
0x180016eb0  cmp     [rdi+0C0h], r14d
0x180016eb7  jnz     short loc_180016ECF
0x180016eb9  mov     r8, r14; Size
0x180016ebc  lea     rcx, [rdi+0B0h]; Buf1
0x180016ec3  mov     rdx, r15; Buf2
0x180016ec6  call    memcmp_0
0x180016ecb  test    eax, eax
0x180016ecd  jz      short loc_180016ED7
0x180016ecf  mov     rdi, rbx
0x180016ed2  test    rsi, rsi
0x180016ed5  jnz     short loc_180016EA6
0x180016ed7  mov     rcx, rbp; lpCriticalSection
0x180016eda  call    cs:__imp_LeaveCriticalSection
0x180016ee1  nop     dword ptr [rax+rax+00h]
0x180016ee6  test    rdi, rdi
0x180016ee9  jnz     short loc_180016EF0
0x180016eeb  lea     ebx, [rdi+2]
0x180016eee  jmp     short loc_180016F64
0x180016ef0  mov     r9, [rdi+0C8h]
0x180016ef7  lea     r8, aMadcapLeaseAdd; "[MADCAP] Lease added back to cache: %s"
0x180016efe  mov     edx, 20000h
0x180016f03  lea     rcx, qword_180039310
0x180016f0a  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x180016f11  nop     dword ptr [rax+rax+00h]
0x180016f16  mov     esi, 1
0x180016f1b  cmp     [rdi+0D0h], ebx
0x180016f21  jz      short loc_180016F49
0x180016f23  mov     r9d, esi
0x180016f26  mov     [rsp+48h+var_28], ebx
0x180016f2a  lea     r8, aPleaseMBavaila; "pLease->m_bAvailable == 0"
0x180016f31  mov     edx, 45Ch
0x180016f36  lea     rcx, aBaseEcoWdsWdss_3; "base\\eco\\wds\\wdssrv\\server\\src\\ma"...
0x180016f3d  call    cs:__imp_?WdsAssert@@YAXPEBDK0HH@Z; WdsAssert(char const *,ulong,char const *,int,int)
0x180016f44  nop     dword ptr [rax+rax+00h]
0x180016f49  xor     ecx, ecx; Time
0x180016f4b  mov     [rdi+0D0h], esi
0x180016f51  call    cs:__imp_time
0x180016f58  nop     dword ptr [rax+rax+00h]
0x180016f5d  mov     [rdi+0D8h], rax
0x180016f64  mov     rcx, rbp; lpCriticalSection
0x180016f67  call    cs:__imp_LeaveCriticalSection
0x180016f6e  nop     dword ptr [rax+rax+00h]
0x180016f73  mov     rbp, [rsp+48h+arg_8]
0x180016f78  mov     eax, ebx
0x180016f7a  mov     rbx, [rsp+48h+arg_0]
0x180016f7f  mov     rsi, [rsp+48h+arg_10]
0x180016f84  add     rsp, 30h
0x180016f88  pop     r15
0x180016f8a  pop     r14
0x180016f8c  pop     rdi
0x180016f8d  retn
```
