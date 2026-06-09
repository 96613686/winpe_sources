# CDVRSink::CDVRSink(HKEY__ *,HKEY__ *,ulong,void * *,int,long *,CTPtrArray<WRITER_SINK_CALLBACK,20> *)

- ea: `0x180001f94`
- end: `0x180002256`
- name: `??0CDVRSink@@QEAA@PEAUHKEY__@@0KPEAPEAXHPEAJPEAV?$CTPtrArray@UWRITER_SINK_CALLBACK@@$0BE@@@@Z`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800051c0`

## callees

- `0x180001f1c`
- `0x180001f94`
- `0x1800030a0`
- `0x1800078c0`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x1800021f6`
- `KERNEL32!GetSystemInfo` at `0x1800021f6`

## pseudocode

```c
__int64 __fastcall CDVRSink::CDVRSink(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5, unsigned int a6, int *a7)
{
  int *v7; // r15
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  _SYSTEM_INFO SystemInfo; // [rsp+20h] [rbp-68h] BYREF

  v7 = a7;
  CWMFileSinkV1::CWMFileSinkV1(a1, a7);
  *(_QWORD *)(a1 + 9328) = a2;
  *(_QWORD *)(a1 + 9280) = 0;
  *(_QWORD *)a1 = &CDVRSink::`vftable'{for `IWMWriterFileSink3'};
  *(_QWORD *)(a1 + 9288) = 0;
  *(_QWORD *)(a1 + 8) = &CDVRSink::`vftable'{for `IWMRegisterCallback'};
  *(_QWORD *)(a1 + 9296) = 0;
  *(_QWORD *)(a1 + 9272) = &CDVRSink::`vftable';
  *(_DWORD *)(a1 + 9352) = -1;
  *(_DWORD *)(a1 + 9348) = 1;
  *(_QWORD *)(a1 + 9304) = 0;
  *(_QWORD *)(a1 + 9336) = a3;
  *(_QWORD *)(a1 + 9360) = 0;
  *(_QWORD *)(a1 + 9368) = 0;
  *(_QWORD *)(a1 + 9376) = 0;
  *(_DWORD *)(a1 + 9384) = 0;
  *(_QWORD *)(a1 + 9440) = 1;
  *(_QWORD *)(a1 + 9392) = &CASFIndexObject::`vftable';
  *(_QWORD *)(a1 + 9400) = 100;
  *(_QWORD *)(a1 + 9432) = 0;
  *(_QWORD *)(a1 + 9392) = &CDVRIndexObject::`vftable';
  v12 = a6;
  *(GUID *)(a1 + 9408) = CLSID_CAsfIndexObjectV2;
  *(_DWORD *)(a1 + 9400) = 108;
  *(_QWORD *)(a1 + 9480) = 0;
  *(_QWORD *)(a1 + 9472) = 0;
  *(_QWORD *)(a1 + 9492) = 0;
  *(_QWORD *)(a1 + 9504) = 0;
  *(_DWORD *)(a1 + 9512) = 0;
  *(_QWORD *)(a1 + 9520) = 0;
  *(_DWORD *)(a1 + 9528) = 0;
  *(_QWORD *)(a1 + 9536) = 0;
  *(_QWORD *)(a1 + 9544) = 0;
  *(_QWORD *)(a1 + 9552) = 0;
  *(_QWORD *)(a1 + 9560) = 0;
  *(_QWORD *)(a1 + 9568) = 0;
  *(_QWORD *)(a1 + 9576) = 0;
  *(_QWORD *)(a1 + 9584) = 0;
  *(_DWORD *)(a1 + 9488) = 56;
  *(_DWORD *)(a1 + 9600) = v12;
  *(_DWORD *)(a1 + 9744) = -1;
  *(_QWORD *)(a1 + 9776) = a5;
  *(_QWORD *)(a1 + 9592) = 0;
  *(_QWORD *)(a1 + 9624) = 0;
  *(_QWORD *)(a1 + 9632) = 0;
  *(_QWORD *)(a1 + 9640) = 0;
  *(_QWORD *)(a1 + 9748) = 0;
  *(_QWORD *)(a1 + 9756) = 0;
  *(_DWORD *)(a1 + 9764) = a4;
  *(_WORD *)(a1 + 9768) = -1;
  *(_DWORD *)(a1 + 8408) = 0;
  *(_OWORD *)(a1 + 9604) = 0;
  *(_OWORD *)(a1 + 9312) = 0;
  memset_0((void *)(a1 + 9648), 0, 0x40u);
  *(_OWORD *)(a1 + 9712) = 0;
  *(_OWORD *)(a1 + 9728) = 0;
  v13 = *(_DWORD *)(a1 + 212);
  if ( *(_DWORD *)(a1 + 9368) )
  {
    v14 = -2147475450;
    v15 = v13 | 7;
  }
  else
  {
    v14 = 0x80000000;
    v15 = v13 & 0xFFFFFFF8 | 3;
  }
  *(_DWORD *)(a1 + 212) = v15;
  *(_DWORD *)(a1 + 208) = v14;
  *(_DWORD *)(a1 + 216) = 2;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  *(_DWORD *)(a1 + 9344) = SystemInfo.dwPageSize;
  while ( 1 )
  {
    v16 = *(_DWORD *)(a1 + 9348);
    if ( (int)CDVRSink::GetMaxIndexEntries((CDVRSink *)(a1 + 9272), v16, &a6) >= 0 )
      break;
    *(_DWORD *)(a1 + 9348) = v16 + 1;
    if ( v16 + 1 > 0xA )
    {
      if ( v7 && *v7 >= 0 )
        *v7 = -2147467259;
      return a1;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180001f94  push    rbx
0x180001f96  push    rbp
0x180001f97  push    rsi
0x180001f98  push    rdi
0x180001f99  push    r12
0x180001f9b  push    r14
0x180001f9d  push    r15
0x180001f9f  sub     rsp, 50h
0x180001fa3  mov     r15, [rsp+88h+arg_30]
0x180001fab  mov     rbx, rdx
0x180001fae  mov     rdx, r15
0x180001fb1  mov     esi, r9d
0x180001fb4  mov     rdi, r8
0x180001fb7  mov     r14, rcx
0x180001fba  call    ??0CWMFileSinkV1@@QEAA@PEAJPEAV?$CTPtrArray@UWRITER_SINK_CALLBACK@@$0BE@@@@Z; CWMFileSinkV1::CWMFileSinkV1(long *,CTPtrArray<WRITER_SINK_CALLBACK,20> *)
0x180001fbf  xor     r12d, r12d
0x180001fc2  mov     [r14+2470h], rbx
0x180001fc9  mov     [r14+2440h], r12
0x180001fd0  lea     rax, ??_7CDVRSink@@6BIWMWriterFileSink3@@@; const CDVRSink::`vftable'{for `IWMWriterFileSink3'}
0x180001fd7  mov     [r14], rax
0x180001fda  lea     rbp, [r14+2438h]
0x180001fe1  mov     [r14+2448h], r12
0x180001fe8  lea     rax, ??_7CDVRSink@@6BIWMRegisterCallback@@@; const CDVRSink::`vftable'{for `IWMRegisterCallback'}
0x180001fef  mov     [r14+8], rax
0x180001ff3  lea     r8d, [r12+40h]; Size
0x180001ff8  mov     [r14+2450h], r12
0x180001fff  lea     rax, ??_7CDVRSink@@6B@; const CDVRSink::`vftable'
0x180002006  mov     [rbp+0], rax
0x18000200a  or      ecx, 0FFFFFFFFh
0x18000200d  mov     [r14+2488h], ecx
0x180002014  lea     eax, [r12+1]
0x180002019  mov     [r14+2484h], eax
0x180002020  xorps   xmm1, xmm1
0x180002023  mov     [r14+2458h], r12
0x18000202a  xor     edx, edx; Val
0x18000202c  mov     [r14+2478h], rdi
0x180002033  mov     [r14+2490h], r12
0x18000203a  mov     [r14+2498h], r12
0x180002041  mov     [r14+24A0h], r12
0x180002048  mov     [r14+24A8h], r12d
0x18000204f  mov     [r14+24E0h], rax
0x180002056  lea     rax, ??_7CASFIndexObject@@6B@; const CASFIndexObject::`vftable'
0x18000205d  mov     [r14+24B0h], rax
0x180002064  lea     rax, ??_7CDVRIndexObject@@6B@; const CDVRIndexObject::`vftable'
0x18000206b  mov     qword ptr [r14+24B8h], 64h ; 'd'
0x180002076  mov     [r14+24D8h], r12
0x18000207d  movups  xmm0, xmmword ptr cs:CLSID_CAsfIndexObjectV2.Data1
0x180002084  mov     [r14+24B0h], rax
0x18000208b  mov     eax, [rsp+88h+arg_28]
0x180002092  movdqu  xmmword ptr [r14+24C0h], xmm0
0x18000209b  mov     dword ptr [r14+24B8h], 6Ch ; 'l'
0x1800020a6  mov     [r14+2508h], r12
0x1800020ad  xorps   xmm0, xmm0
0x1800020b0  mov     [r14+2500h], r12
0x1800020b7  mov     [r14+2514h], r12
0x1800020be  mov     [r14+2520h], r12
0x1800020c5  mov     [r14+2528h], r12d
0x1800020cc  mov     [r14+2530h], r12
0x1800020d3  mov     [r14+2538h], r12d
0x1800020da  mov     [r14+2540h], r12
0x1800020e1  mov     [r14+2548h], r12
0x1800020e8  mov     [r14+2550h], r12
0x1800020ef  mov     [r14+2558h], r12
0x1800020f6  mov     [r14+2560h], r12
0x1800020fd  mov     [r14+2568h], r12
0x180002104  mov     [r14+2570h], r12
0x18000210b  mov     dword ptr [r14+2510h], 38h ; '8'
0x180002116  mov     [r14+2580h], eax
0x18000211d  mov     rax, [rsp+88h+arg_20]
0x180002125  mov     [r14+2610h], ecx
0x18000212c  lea     rcx, [r14+25B0h]; void *
0x180002133  mov     [r14+2630h], rax
0x18000213a  mov     [r14+2578h], r12
0x180002141  mov     [r14+2598h], r12
0x180002148  mov     [r14+25A0h], r12
0x18000214f  mov     [r14+25A8h], r12
0x180002156  mov     [r14+2614h], r12
0x18000215d  mov     [r14+261Ch], r12
0x180002164  mov     [r14+2624h], esi
0x18000216b  mov     word ptr [r14+2628h], 0FFFFh
0x180002175  mov     [r14+20D8h], r12d
0x18000217c  movups  xmmword ptr [r14+2584h], xmm0
0x180002184  movups  xmmword ptr [r14+2460h], xmm1
0x18000218c  call    memset_0
0x180002191  xorps   xmm0, xmm0
0x180002194  movups  xmmword ptr [r14+25F0h], xmm0
0x18000219c  movups  xmmword ptr [r14+2600h], xmm0
0x1800021a4  mov     eax, [r14+0D4h]
0x1800021ab  cmp     [r14+2498h], r12d
0x1800021b2  jz      short loc_1800021BE
0x1800021b4  mov     ecx, 80002006h
0x1800021b9  or      eax, 7
0x1800021bc  jmp     short loc_1800021C9
0x1800021be  and     eax, 0FFFFFFFBh
0x1800021c1  mov     ecx, 80000000h
0x1800021c6  or      eax, 3
0x1800021c9  mov     [r14+0D4h], eax
0x1800021d0  mov     [r14+0D0h], ecx
0x1800021d7  lea     rcx, [rsp+88h+SystemInfo]; lpSystemInfo
0x1800021dc  mov     dword ptr [r14+0D8h], 2
0x1800021e7  movups  xmmword ptr [rsp+88h+SystemInfo], xmm0
0x1800021ec  movups  xmmword ptr [rsp+88h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800021f1  movups  xmmword ptr [rsp+88h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800021f6  call    cs:__imp_GetSystemInfo
0x1800021fc  mov     eax, [rsp+88h+SystemInfo.dwPageSize]
0x180002200  mov     [r14+2480h], eax
0x180002207  mov     ebx, [r14+2484h]
0x18000220e  lea     r8, [rsp+88h+arg_28]; unsigned int *
0x180002216  mov     edx, ebx; unsigned int
0x180002218  mov     rcx, rbp; this
0x18000221b  call    ?GetMaxIndexEntries@CDVRSink@@UEAAJKPEAK@Z; CDVRSink::GetMaxIndexEntries(ulong,ulong *)
0x180002220  test    eax, eax
0x180002222  jns     short loc_180002244
0x180002224  lea     eax, [rbx+1]
0x180002227  mov     [r14+2484h], eax
0x18000222e  cmp     eax, 0Ah
0x180002231  jbe     short loc_180002207
0x180002233  test    r15, r15
0x180002236  jz      short loc_180002244
0x180002238  cmp     [r15], r12d
0x18000223b  jl      short loc_180002244
0x18000223d  mov     dword ptr [r15], 80004005h
0x180002244  mov     rax, r14
0x180002247  add     rsp, 50h
0x18000224b  pop     r15
0x18000224d  pop     r14
0x18000224f  pop     r12
0x180002251  pop     rdi
0x180002252  pop     rsi
0x180002253  pop     rbp
0x180002254  pop     rbx
0x180002255  retn
```
