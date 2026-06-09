# CMulticastNamespace::Cleanup(void)

- ea: `0x180003868`
- end: `0x180003997`
- name: `?Cleanup@CMulticastNamespace@@QEAAXXZ`
- size: `303`
- prototype: `void __fastcall(CMulticastNamespace *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180005a4c`
- `0x180007a24`

## callees

- `0x180003868`
- `0x180003b08`
- `0x180004184`
- `0x180004438`
- `0x1800044e8`
- `0x18000b430`
- `0x18001a9a8`
- `0x1800226e4`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180003990`
- `KERNEL32!EnterCriticalSection` at `0x180003883`
- `KERNEL32!EnterCriticalSection` at `0x180003883`
- `KERNEL32!DeleteCriticalSection` at `0x18000390c`
- `KERNEL32!DeleteCriticalSection` at `0x18000390c`

## pseudocode

```c
void __fastcall CMulticastNamespace::Cleanup(CMulticastNamespace *this)
{
  struct _RTL_CRITICAL_SECTION **v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdx
  struct _RTL_CRITICAL_SECTION *DebugInfo; // rbx
  unsigned __int64 v7; // rax
  struct _RTL_CRITICAL_SECTION *v8; // [rsp+30h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v2 = (struct _RTL_CRITICAL_SECTION **)((char *)this + 424);
  v3 = *((_QWORD *)this + 53);
  if ( v3 )
  {
    v4 = *((_QWORD *)this + 53);
    v5 = v4;
    do
    {
      v3 = *(_QWORD *)(v3 + 3080);
      CMulticastContent::Cleanup((LPCRITICAL_SECTION)(v5 & -(__int64)(v4 != 0)));
      v4 = v3;
      v5 = v3;
    }
    while ( v3 );
    DebugInfo = *v2;
    if ( *v2 )
    {
      v8 = *v2;
      do
      {
        if ( (unsigned int)CMulticastContent::CanDelete(DebugInfo) )
        {
          CList<CMulticastContent,CNoLock>::DeleteAt((char *)this + 424, &v8);
          CMulticastContent::Shutdown(DebugInfo);
          if ( DebugInfo )
          {
            CMulticastContent::Shutdown(DebugInfo);
            CMcCoClients::Shutdown((CMcCoClients *)&DebugInfo[7].SpinCount);
            DeleteCriticalSection(DebugInfo);
            operator delete(DebugInfo);
          }
          v7 = CDate::FileTimeToMSec(0);
          DebugInfo = v8;
          *((_QWORD *)this + 56) = v7;
        }
        else
        {
          DebugInfo = (struct _RTL_CRITICAL_SECTION *)DebugInfo[77].DebugInfo;
          v8 = DebugInfo;
        }
      }
      while ( DebugInfo );
    }
  }
  if ( *((_DWORD *)this + 18) == 2
    && *((_DWORD *)this + 35)
    && !*((_DWORD *)this + 111)
    && CDate::FileTimeToMSec(0) - *((_QWORD *)this + 56) >= *((unsigned int *)this + 81) )
  {
    *((_DWORD *)this + 30) = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180003868  mov     [rsp+arg_8], rbx
0x18000386d  mov     [rsp+arg_10], rbp
0x180003872  mov     [rsp+arg_18], rsi
0x180003877  push    rdi
0x180003878  sub     rsp, 20h
0x18000387c  mov     rdi, rcx
0x18000387f  add     rcx, 10h; lpCriticalSection
0x180003883  call    cs:__imp_EnterCriticalSection
0x180003889  lea     rsi, [rdi+1A8h]
0x180003890  mov     rbx, [rsi]
0x180003893  test    rbx, rbx
0x180003896  jz      loc_180003940
0x18000389c  mov     rax, rbx
0x18000389f  mov     rdx, rbx
0x1800038a2  mov     rbx, [rbx+0C08h]
0x1800038a9  neg     rax
0x1800038ac  sbb     rcx, rcx
0x1800038af  and     rcx, rdx; lpCriticalSection
0x1800038b2  call    ?Cleanup@CMulticastContent@@QEAAXXZ; CMulticastContent::Cleanup(void)
0x1800038b7  mov     rax, rbx
0x1800038ba  mov     rdx, rbx
0x1800038bd  test    rbx, rbx
0x1800038c0  jnz     short loc_1800038A2
0x1800038c2  mov     rbx, [rsi]
0x1800038c5  test    rbx, rbx
0x1800038c8  jz      short loc_180003940
0x1800038ca  mov     [rsp+28h+arg_0], rbx
0x1800038cf  mov     rcx, rbx; lpCriticalSection
0x1800038d2  call    ?CanDelete@CMulticastContent@@QEAAHXZ; CMulticastContent::CanDelete(void)
0x1800038d7  test    eax, eax
0x1800038d9  jz      short loc_18000392F
0x1800038db  lea     rdx, [rsp+28h+arg_0]
0x1800038e0  mov     rcx, rsi
0x1800038e3  call    ?DeleteAt@?$CList@VCMulticastContent@@VCNoLock@@@@QEAAPEAVCMulticastContent@@AEAPEAX@Z; CList<CMulticastContent,CNoLock>::DeleteAt(void * &)
0x1800038e8  mov     rcx, rbx; lpCriticalSection
0x1800038eb  call    ?Shutdown@CMulticastContent@@QEAAKXZ; CMulticastContent::Shutdown(void)
0x1800038f0  test    rbx, rbx
0x1800038f3  jz      short loc_18000391A
0x1800038f5  mov     rcx, rbx; lpCriticalSection
0x1800038f8  call    ?Shutdown@CMulticastContent@@QEAAKXZ; CMulticastContent::Shutdown(void)
0x1800038fd  lea     rcx, [rbx+138h]; this
0x180003904  call    ?Shutdown@CMcCoClients@@QEAAKXZ; CMcCoClients::Shutdown(void)
0x180003909  mov     rcx, rbx; lpCriticalSection
0x18000390c  call    cs:__imp_DeleteCriticalSection
0x180003912  mov     rcx, rbx; void *
0x180003915  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000391a  xor     ecx, ecx; struct _FILETIME *
0x18000391c  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x180003921  mov     rbx, [rsp+28h+arg_0]
0x180003926  mov     [rdi+1C0h], rax
0x18000392d  jmp     short loc_18000393B
0x18000392f  mov     rbx, [rbx+0C08h]
0x180003936  mov     [rsp+28h+arg_0], rbx
0x18000393b  test    rbx, rbx
0x18000393e  jnz     short loc_1800038CF
0x180003940  cmp     dword ptr [rdi+48h], 2
0x180003944  jnz     short loc_180003978
0x180003946  cmp     dword ptr [rdi+8Ch], 0
0x18000394d  jz      short loc_180003978
0x18000394f  cmp     dword ptr [rdi+1BCh], 0
0x180003956  jnz     short loc_180003978
0x180003958  xor     ecx, ecx; struct _FILETIME *
0x18000395a  call    ?FileTimeToMSec@CDate@@SA_KPEAU_FILETIME@@@Z; CDate::FileTimeToMSec(_FILETIME *)
0x18000395f  sub     rax, [rdi+1C0h]
0x180003966  mov     edx, [rdi+144h]
0x18000396c  cmp     rax, rdx
0x18000396f  jb      short loc_180003978
0x180003971  mov     dword ptr [rdi+78h], 1
0x180003978  lea     rcx, [rdi+10h]
0x18000397c  mov     rbx, [rsp+28h+arg_8]
0x180003981  mov     rbp, [rsp+28h+arg_10]
0x180003986  mov     rsi, [rsp+28h+arg_18]
0x18000398b  add     rsp, 20h
0x18000398f  pop     rdi
0x180003990  jmp     cs:__imp_LeaveCriticalSection
```
