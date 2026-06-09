# HUBDSM_GettingMSOSExtendedDescriptor

- ea: `0x140022500`
- end: `0x1400225f8`
- name: `HUBDSM_GettingMSOSExtendedDescriptor`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14000a53c`
- `0x140022500`
- `0x14002b128`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140022527`
- `ntoskrnl!ExAllocatePool2` at `0x140022527`

## pseudocode

```c
__int64 __fastcall HUBDSM_GettingMSOSExtendedDescriptor(__int64 a1)
{
  __int64 v1; // rbx
  __int64 Pool2; // rax
  int v3; // edx
  __int64 v4; // r8
  int MsOsFeatureDescriptor; // eax
  __int64 v7; // [rsp+28h] [rbp-10h]

  v1 = *(_QWORD *)(a1 + 960);
  Pool2 = ExAllocatePool2(64, *(unsigned int *)(v1 + 1740), 1681082453);
  *(_QWORD *)(v1 + 2112) = Pool2;
  if ( Pool2 )
  {
    MsOsFeatureDescriptor = HUBDTX_GetMsOsFeatureDescriptor(v1, 0, v4, 4, Pool2, *(unsigned int *)(v1 + 1740));
    if ( MsOsFeatureDescriptor >= 0 )
      return 1000;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_(
        *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
        v3,
        5,
        63,
        (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids);
    }
    MsOsFeatureDescriptor = -1073741823;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v7) = MsOsFeatureDescriptor;
    LOBYTE(v3) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*(_QWORD *)(v1 + 8) + 1432LL),
      v3,
      5,
      64,
      (__int64)WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids,
      v7);
  }
  HUBSM_AddEvent(v1 + 512, 4004);
  return 1000;
}

```

## disassembly

```asm
0x140022500  mov     [rsp+arg_0], rbx
0x140022505  mov     [rsp+arg_8], rbp
0x14002250a  push    rdi
0x14002250b  sub     rsp, 30h
0x14002250f  mov     rbx, [rcx+3C0h]
0x140022516  mov     r8d, 64334855h
0x14002251c  mov     ecx, 40h ; '@'
0x140022521  mov     edx, [rbx+6CCh]
0x140022527  call    cs:__imp_ExAllocatePool2
0x14002252e  nop     dword ptr [rax+rax+00h]
0x140022533  mov     [rbx+840h], rax
0x14002253a  mov     rcx, rax
0x14002253d  lea     rdi, WPP_RECORDER_INITIALIZED
0x140022544  lea     rbp, WPP_736cb17edbb73fe74dd9f642bb1bec68_Traceguids
0x14002254b  test    rax, rax
0x14002254e  jnz     short loc_14002257F
0x140022550  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140022557  jz      short loc_140022578
0x140022559  mov     rcx, [rbx+8]
0x14002255d  lea     r9d, [rax+3Fh]
0x140022561  lea     r8d, [rax+5]
0x140022565  mov     [rsp+38h+var_18], rbp
0x14002256a  mov     dl, 2
0x14002256c  mov     rcx, [rcx+598h]
0x140022573  call    WPP_RECORDER_SF_
0x140022578  mov     eax, 0C0000001h
0x14002257d  jmp     short loc_1400225A3
0x14002257f  mov     eax, [rbx+6CCh]
0x140022585  mov     r9d, 4
0x14002258b  mov     [rsp+38h+var_10], rax
0x140022590  xor     edx, edx
0x140022592  mov     [rsp+38h+var_18], rcx
0x140022597  mov     rcx, rbx
0x14002259a  call    HUBDTX_GetMsOsFeatureDescriptor
0x14002259f  test    eax, eax
0x1400225a1  jns     short loc_1400225E2
0x1400225a3  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400225aa  jz      short loc_1400225D1
0x1400225ac  mov     rcx, [rbx+8]
0x1400225b0  mov     r9d, 40h ; '@'
0x1400225b6  mov     dword ptr [rsp+38h+var_10], eax
0x1400225ba  mov     dl, 2
0x1400225bc  mov     [rsp+38h+var_18], rbp
0x1400225c1  mov     rcx, [rcx+598h]
0x1400225c8  lea     r8d, [r9-3Bh]
0x1400225cc  call    WPP_RECORDER_SF_d
0x1400225d1  lea     rcx, [rbx+200h]
0x1400225d8  mov     edx, 0FA4h
0x1400225dd  call    HUBSM_AddEvent
0x1400225e2  mov     rbx, [rsp+38h+arg_0]
0x1400225e7  mov     eax, 3E8h
0x1400225ec  mov     rbp, [rsp+38h+arg_8]
0x1400225f1  add     rsp, 30h
0x1400225f5  pop     rdi
0x1400225f6  retn
```
