# SrvNetUpdateIPAddressListWorkerRoutine

- ea: `0x140050270`
- end: `0x140050631`
- name: `SrvNetUpdateIPAddressListWorkerRoutine`
- size: `961`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140005e10`
- `0x140007700`
- `0x140007ec0`
- `0x14000d230`
- `0x14001389c`
- `0x140015790`
- `0x14002a3e0`
- `0x14002a540`
- `0x140050270`

## import_xrefs

- `ntoskrnl!IoQueueWorkItemEx` at `0x1400505ac`
- `ntoskrnl!IoQueueWorkItemEx` at `0x1400505ac`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1400504d6`
- `ntoskrnl!IoUninitializeWorkItem` at `0x1400504d6`
- `ntoskrnl!ExAllocatePool2` at `0x140050304`
- `ntoskrnl!ExAllocatePool2` at `0x140050304`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005049b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005049b`
- `NETIO!FreeMibTable` at `0x140050475`
- `NETIO!FreeMibTable` at `0x140050475`
- `NETIO!GetUnicastIpAddressTable` at `0x1400502e0`
- `NETIO!GetUnicastIpAddressTable` at `0x1400502e0`

## pseudocode

```c
void __fastcall SrvNetUpdateIPAddressListWorkerRoutine(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  NTSTATUS UnicastIpAddressTable; // eax
  char *Pool2; // rax
  char *v6; // rsi
  unsigned int v7; // ebp
  char *v8; // r15
  ULONG i; // ebx
  char *v10; // rdi
  int v11; // eax
  __int64 v12; // r9
  int v13; // eax
  signed __int32 v14; // eax
  signed __int32 v15; // ett
  PDEVICE_OBJECT v16; // r10
  __int64 v17; // rdx
  unsigned int v18; // [rsp+20h] [rbp-158h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+28h] [rbp-150h] BYREF
  __int128 v20; // [rsp+30h] [rbp-148h] BYREF
  _BYTE Src[256]; // [rsp+40h] [rbp-138h] BYREF

  v18 = 127;
  Table = 0;
  _InterlockedExchange(&SrvNetIpAddressUpdateWorkerState, 2);
  v20 = 0;
  UnicastIpAddressTable = GetUnicastIpAddressTable(0, &Table);
  if ( UnicastIpAddressTable < 0 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        59,
        WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids,
        (unsigned int)UnicastIpAddressTable);
    }
  }
  else
  {
    Pool2 = (char *)ExAllocatePool2(64, 32512, 1717719884);
    v6 = Pool2;
    if ( Pool2 )
    {
      memmove(Pool2, L"127.0.0.1", 0x12u);
      *((_WORD *)v6 + 9) = 0;
      memmove(v6 + 20, L"::1", 6u);
      *((_WORD *)v6 + 13) = 0;
      v7 = 16242;
      v8 = v6 + 28;
      for ( i = 0; i < Table->NumEntries; ++i )
      {
        v10 = (char *)Table + 80 * i;
        if ( !(unsigned __int8)SrvNetSkipAddress(v10 + 8) )
        {
          v18 = 127;
          v11 = SrvNetIpAddressToString(v10 + 8, Src, &v18);
          v12 = (unsigned int)v11;
          if ( v11 < 0 )
          {
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) )
            {
              v17 = 61;
LABEL_36:
              WPP_SF_d(v16->AttachedDevice, v17, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids, v12);
              goto LABEL_11;
            }
            goto LABEL_11;
          }
          if ( v7 < v18 )
            break;
          memmove(v8, Src, 2LL * v18);
          v7 -= v18;
          v8 += 2 * v18;
        }
      }
      *((_QWORD *)&v20 + 1) = v6;
      LOWORD(v20) = 2 * (16256 - v7);
      WORD1(v20) = v20;
      v13 = SrvLibAllocateNameList(&v20, 0, &SrvAdminNameLock, &SrvAdminIpAddressList);
      if ( v13 < 0 )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v17 = 62;
          v12 = (unsigned int)v13;
          goto LABEL_36;
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids);
    }
  }
LABEL_11:
  if ( Table )
  {
    FreeMibTable(Table);
    Table = 0;
  }
  if ( v6 )
    ExFreePoolWithTag(v6, 0x6662534Cu);
  _m_prefetchw(&SrvNetIpAddressUpdateWorkerState);
  v14 = SrvNetIpAddressUpdateWorkerState;
  do
  {
    v15 = v14;
    v14 = _InterlockedCompareExchange(&SrvNetIpAddressUpdateWorkerState, v14 & 0xFFFFFFFD, v14);
  }
  while ( v15 != v14 );
  if ( (v14 & 1) != 0 )
  {
    IoQueueWorkItemEx(IoWorkItem, SrvNetUpdateIPAddressListWorkerRoutine, DelayedWorkQueue, 0);
  }
  else
  {
    IoUninitializeWorkItem(IoWorkItem);
    SrvNetWskNotifyCleanupProviderContext(IoWorkItem);
  }
}

```

## disassembly

```asm
0x140050270  mov     r11, rsp
0x140050273  push    r14
0x140050275  sub     rsp, 170h
0x14005027c  mov     rax, cs:__security_cookie
0x140050283  xor     rax, rsp
0x140050286  mov     [rsp+178h+var_38], rax
0x14005028e  mov     [r11+10h], rbp
0x140050292  lea     rdx, [rsp+178h+Table]; Table
0x140050297  xor     eax, eax
0x140050299  mov     [r11+20h], rsi
0x14005029d  mov     [rsp+178h+var_144], eax
0x1400502a1  xorps   xmm0, xmm0
0x1400502a4  mov     [rsp+178h+var_144], eax
0x1400502a8  xor     ecx, ecx; Family
0x1400502aa  mov     [r11-18h], r12
0x1400502ae  mov     eax, 2
0x1400502b3  mov     [r11-20h], r13
0x1400502b7  mov     r14, r8
0x1400502ba  mov     [rsp+178h+var_158], 7Fh
0x1400502c2  xor     r13d, r13d
0x1400502c5  mov     [rsp+178h+Table], r13
0x1400502ca  mov     r12d, 12h
0x1400502d0  xchg    eax, cs:SrvNetIpAddressUpdateWorkerState
0x1400502d6  mov     ebp, 6
0x1400502db  movups  xmmword ptr [rsp+30h], xmm0
0x1400502e0  call    cs:__imp_GetUnicastIpAddressTable
0x1400502e7  nop     dword ptr [rax+rax+00h]
0x1400502ec  test    eax, eax
0x1400502ee  js      loc_140050505
0x1400502f4  mov     edx, 7F00h
0x1400502f9  mov     ecx, 40h ; '@'
0x1400502fe  mov     r8d, 6662534Ch
0x140050304  call    cs:__imp_ExAllocatePool2
0x14005030b  nop     dword ptr [rax+rax+00h]
0x140050310  mov     rsi, rax
0x140050313  test    rax, rax
0x140050316  jz      loc_140050555
0x14005031c  mov     [rsp+178h+arg_0], rbx
0x140050324  lea     rdx, a127001; "127.0.0.1"
0x14005032b  movzx   ebx, r12w
0x14005032f  mov     rcx, rax; void *
0x140050332  mov     r8d, ebx; Size
0x140050335  mov     [rsp+178h+var_10], rdi
0x14005033d  mov     [rsp+178h+var_28], r15
0x140050345  call    memmove
0x14005034a  shr     rbx, 1
0x14005034d  lea     rdx, a1; "::1"
0x140050354  mov     [rsi+rbx*2], r13w
0x140050359  inc     rbx
0x14005035c  lea     rdi, [rsi+rbx*2]
0x140050360  movzx   ebx, bp
0x140050363  mov     r8d, ebx; Size
0x140050366  mov     rcx, rdi; void *
0x140050369  call    memmove
0x14005036e  mov     eax, ebp
0x140050370  shr     rbx, 1
0x140050373  shr     eax, 1
0x140050375  mov     ebp, 3F7Eh
0x14005037a  sub     ebp, eax
0x14005037c  mov     eax, r12d
0x14005037f  shr     eax, 1
0x140050381  lea     r15, [rbx+1]
0x140050385  mov     [rdi+rbx*2], r13w
0x14005038a  sub     ebp, eax
0x14005038c  lea     r15, [rdi+r15*2]
0x140050390  mov     ebx, r13d
0x140050393  mov     rdx, [rsp+178h+Table]
0x140050398  cmp     ebx, [rdx]
0x14005039a  jnb     short loc_140050407
0x14005039c  mov     eax, ebx
0x14005039e  lea     rdi, [rax+rax*4]
0x1400503a2  shl     rdi, 4
0x1400503a6  add     rdi, rdx
0x1400503a9  lea     rcx, [rdi+8]
0x1400503ad  call    SrvNetSkipAddress
0x1400503b2  test    al, al
0x1400503b4  jz      short loc_1400503BA
0x1400503b6  inc     ebx
0x1400503b8  jmp     short loc_140050393
0x1400503ba  lea     r8, [rsp+178h+var_158]
0x1400503bf  mov     [rsp+178h+var_158], 7Fh
0x1400503c7  lea     rdx, [rsp+178h+Src]
0x1400503cc  lea     rcx, [rdi+8]
0x1400503d0  call    SrvNetIpAddressToString
0x1400503d5  mov     r9d, eax
0x1400503d8  test    eax, eax
0x1400503da  js      loc_1400505BD
0x1400503e0  mov     eax, [rsp+178h+var_158]
0x1400503e4  cmp     ebp, eax
0x1400503e6  jb      short loc_140050407
0x1400503e8  mov     r8d, eax
0x1400503eb  lea     rdx, [rsp+178h+Src]; Src
0x1400503f0  add     r8, r8; Size
0x1400503f3  mov     rcx, r15; void *
0x1400503f6  call    memmove
0x1400503fb  mov     ecx, [rsp+178h+var_158]
0x1400503ff  sub     ebp, ecx
0x140050401  lea     r15, [r15+rcx*2]
0x140050405  jmp     short loc_1400503B6
0x140050407  mov     eax, 3F80h
0x14005040c  mov     [rsp+178h+var_140], rsi
0x140050411  sub     ax, bp
0x140050414  lea     r9, SrvAdminIpAddressList
0x14005041b  add     ax, ax
0x14005041e  lea     r8, SrvAdminNameLock
0x140050425  xor     edx, edx
0x140050427  mov     [rsp+178h+var_148], ax
0x14005042c  lea     rcx, [rsp+178h+var_148]
0x140050431  mov     [rsp+178h+var_146], ax
0x140050436  call    SrvLibAllocateNameList
0x14005043b  test    eax, eax
0x14005043d  js      loc_1400505F5
0x140050443  mov     rdi, [rsp+178h+var_10]
0x14005044b  mov     rbx, [rsp+178h+arg_0]
0x140050453  mov     r15, [rsp+178h+var_28]
0x14005045b  mov     rcx, [rsp+178h+Table]; Memory
0x140050460  mov     r12, [rsp+178h+var_18]
0x140050468  mov     rbp, [rsp+178h+arg_8]
0x140050470  test    rcx, rcx
0x140050473  jz      short loc_140050486
0x140050475  call    cs:__imp_FreeMibTable
0x14005047c  nop     dword ptr [rax+rax+00h]
0x140050481  mov     [rsp+178h+Table], r13
0x140050486  mov     r13, [rsp+178h+var_20]
0x14005048e  test    rsi, rsi
0x140050491  jz      short loc_1400504A7
0x140050493  mov     edx, 6662534Ch; Tag
0x140050498  mov     rcx, rsi; P
0x14005049b  call    cs:__imp_ExFreePoolWithTag
0x1400504a2  nop     dword ptr [rax+rax+00h]
0x1400504a7  prefetchw byte ptr cs:SrvNetIpAddressUpdateWorkerState
0x1400504ae  mov     eax, cs:SrvNetIpAddressUpdateWorkerState
0x1400504b4  mov     rsi, [rsp+178h+arg_18]
0x1400504bc  mov     edx, eax
0x1400504be  and     edx, 0FFFFFFFDh
0x1400504c1  lock cmpxchg cs:SrvNetIpAddressUpdateWorkerState, edx
0x1400504c9  jnz     short loc_1400504BC
0x1400504cb  mov     rcx, r14; IoWorkItem
0x1400504ce  test    al, 1
0x1400504d0  jnz     loc_14005059C
0x1400504d6  call    cs:__imp_IoUninitializeWorkItem
0x1400504dd  nop     dword ptr [rax+rax+00h]
0x1400504e2  mov     rcx, r14
0x1400504e5  call    SrvNetWskNotifyCleanupProviderContext
0x1400504ea  mov     rcx, [rsp+178h+var_38]
0x1400504f2  xor     rcx, rsp; StackCookie
0x1400504f5  call    __security_check_cookie
0x1400504fa  add     rsp, 170h
0x140050501  pop     r14
0x140050503  retn
0x140050505  mov     rsi, r13
0x140050508  mov     r10, cs:WPP_GLOBAL_Control
0x14005050f  lea     rcx, WPP_GLOBAL_Control
0x140050516  cmp     r10, rcx
0x140050519  jz      loc_14005045B
0x14005051f  test    dword ptr [r10+2Ch], 2000h
0x140050527  jz      loc_14005045B
0x14005052d  cmp     byte ptr [r10+29h], 1
0x140050532  jb      loc_14005045B
0x140050538  mov     rcx, [r10+18h]
0x14005053c  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140050543  mov     edx, 3Bh ; ';'
0x140050548  mov     r9d, eax
0x14005054b  call    WPP_SF_d
0x140050550  jmp     loc_14005045B
0x140050555  mov     rax, cs:WPP_GLOBAL_Control
0x14005055c  lea     rcx, WPP_GLOBAL_Control
0x140050563  cmp     rax, rcx
0x140050566  jz      loc_14005045B
0x14005056c  mov     ecx, [rax+2Ch]
0x14005056f  test    cl, 10h
0x140050572  jz      loc_14005045B
0x140050578  cmp     byte ptr [rax+29h], 1
0x14005057c  jb      loc_14005045B
0x140050582  mov     rcx, [rax+18h]
0x140050586  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x14005058d  mov     edx, 3Ch ; '<'
0x140050592  call    WPP_SF_
0x140050597  jmp     loc_14005045B
0x14005059c  xor     r9d, r9d; Context
0x14005059f  lea     rdx, SrvNetUpdateIPAddressListWorkerRoutine; WorkerRoutine
0x1400505a6  mov     r8d, 1; QueueType
0x1400505ac  call    cs:__imp_IoQueueWorkItemEx
0x1400505b3  nop     dword ptr [rax+rax+00h]
0x1400505b8  jmp     loc_1400504EA
0x1400505bd  mov     r10, cs:WPP_GLOBAL_Control
0x1400505c4  lea     rcx, WPP_GLOBAL_Control
0x1400505cb  cmp     r10, rcx
0x1400505ce  jz      loc_140050443
0x1400505d4  mov     eax, [r10+2Ch]
0x1400505d8  test    al, 10h
0x1400505da  jz      loc_140050443
0x1400505e0  cmp     byte ptr [r10+29h], 1
0x1400505e5  jb      loc_140050443
0x1400505eb  mov     edx, 3Dh ; '='
0x1400505f0  jmp     loc_14005764A
0x1400505f5  mov     r10, cs:WPP_GLOBAL_Control
0x1400505fc  lea     rcx, WPP_GLOBAL_Control
0x140050603  cmp     r10, rcx
0x140050606  jz      loc_140050443
0x14005060c  mov     ecx, [r10+2Ch]
0x140050610  test    cl, 10h
0x140050613  jz      loc_140050443
0x140050619  cmp     byte ptr [r10+29h], 1
0x14005061e  jb      loc_140050443
0x140050624  mov     edx, 3Eh ; '>'
0x140050629  mov     r9d, eax
0x14005062c  jmp     loc_14005764A
0x14005764a  mov     rcx, [r10+18h]
0x14005764e  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140057655  call    WPP_SF_d
0x14005765a  nop
0x14005765b  jmp     loc_140050443
```
