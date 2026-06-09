# SrvAdminSMBSharesReportingRoutine

- ea: `0x140022530`
- end: `0x1400227c6`
- name: `SrvAdminSMBSharesReportingRoutine`
- size: `662`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140001008`
- `0x140001040`
- `0x140005470`
- `0x1400054f0`
- `0x140015790`
- `0x140021880`
- `0x140022530`
- `0x14002a3e0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400225d7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400225e9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400225d7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400225e9`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140022768`
- `ntoskrnl!RtlEnumerateGenericTableLikeADirectory` at `0x140022768`
- `ntoskrnl!ExReleaseResourceLite` at `0x140022784`
- `ntoskrnl!ExReleaseResourceLite` at `0x140022793`
- `ntoskrnl!ExReleaseResourceLite` at `0x140022784`
- `ntoskrnl!ExReleaseResourceLite` at `0x140022793`

## pseudocode

```c
void SrvAdminSMBSharesReportingRoutine()
{
  __int64 v0; // rax
  __int64 v1; // rbx
  struct _ERESOURCE *v2; // r14
  unsigned int **i; // rax
  unsigned int *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int **v8; // rsi
  ULONG DeleteCount; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v10; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v11; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v12; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v13; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v14; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v15; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v16; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned int v17; // [rsp+60h] [rbp-A0h] BYREF
  PVOID RestartKey; // [rsp+68h] [rbp-98h] BYREF
  __int128 Buffer; // [rsp+70h] [rbp-90h] BYREF
  __int128 v20; // [rsp+80h] [rbp-80h]
  __int64 v21; // [rsp+90h] [rbp-70h]
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int *v23; // [rsp+C0h] [rbp-40h]
  __int64 v24; // [rsp+C8h] [rbp-38h]
  unsigned int *v25; // [rsp+D0h] [rbp-30h]
  __int64 v26; // [rsp+D8h] [rbp-28h]
  unsigned int *v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+E8h] [rbp-18h]
  unsigned int *v29; // [rsp+F0h] [rbp-10h]
  __int64 v30; // [rsp+F8h] [rbp-8h]
  unsigned int *v31; // [rsp+100h] [rbp+0h]
  __int64 v32; // [rsp+108h] [rbp+8h]
  unsigned int *v33; // [rsp+110h] [rbp+10h]
  __int64 v34; // [rsp+118h] [rbp+18h]
  unsigned int *v35; // [rsp+120h] [rbp+20h]
  __int64 v36; // [rsp+128h] [rbp+28h]
  unsigned int *v37; // [rsp+130h] [rbp+30h]
  __int64 v38; // [rsp+138h] [rbp+38h]

  RestartKey = 0;
  DeleteCount = 0;
  v21 = 0;
  Buffer = 0;
  v20 = 0;
  v0 = SrvAdminInstanceGetFromType(0);
  v1 = v0;
  if ( v0 )
  {
    v2 = (struct _ERESOURCE *)(v0 + 200);
    ExAcquireResourceSharedLite((PERESOURCE)(v0 + 200), 1u);
    ExAcquireResourceSharedLite((PERESOURCE)(v1 + 96), 1u);
    v21 = 0;
    Buffer = 0;
    v20 = 0;
    for ( i = (unsigned int **)RtlEnumerateGenericTableLikeADirectory(
                                 (PRTL_AVL_TABLE)(v1 + 408),
                                 0,
                                 0,
                                 1u,
                                 &RestartKey,
                                 &DeleteCount,
                                 &Buffer);
          ;
          i = (unsigned int **)RtlEnumerateGenericTableLikeADirectory(
                                 (PRTL_AVL_TABLE)(v1 + 408),
                                 0,
                                 0,
                                 1u,
                                 &RestartKey,
                                 &DeleteCount,
                                 v8) )
    {
      v8 = i;
      if ( !i )
        break;
      v4 = i[4];
      if ( (unsigned int)dword_140036120 > 5 && (unsigned __int8)tlgKeywordOn() )
      {
        v10 = v4[30];
        v23 = &v10;
        v11 = v4[28];
        v25 = &v11;
        v12 = v4[31];
        v27 = &v12;
        v13 = v4[32];
        v29 = &v13;
        v14 = v4[33];
        v31 = &v14;
        v15 = v4[34];
        v33 = &v15;
        v16 = v4[35];
        v35 = &v16;
        v17 = v4[37];
        v37 = &v17;
        v24 = 4;
        v26 = 4;
        v28 = 4;
        v30 = 4;
        v32 = 4;
        v34 = 4;
        v36 = 4;
        v38 = 4;
        tlgWriteTransfer_EtwWriteTransfer(v5, (unsigned __int8 *)&word_140031B3A, v6, v7, 0xAu, &v22);
      }
      InterlockedMinNoFence(v4 + 28, v4[27]);
      InterlockedMinNoFence(v4 + 30, v4[29]);
    }
    ExReleaseResourceLite((PERESOURCE)(v1 + 96));
    ExReleaseResourceLite(v2);
    SrvAdminDereferenceInstance(v1);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids);
  }
}

```

## disassembly

```asm
0x140022530  push    rbp
0x140022532  push    rbx
0x140022533  push    rsi
0x140022534  push    rdi
0x140022535  push    r12
0x140022537  push    r14
0x140022539  push    r15
0x14002253b  lea     rbp, [rsp-50h]
0x140022540  sub     rsp, 150h
0x140022547  mov     rax, cs:__security_cookie
0x14002254e  xor     rax, rsp
0x140022551  mov     [rbp+80h+var_40], rax
0x140022555  xorps   xmm0, xmm0
0x140022558  mov     [rsp+180h+var_118], 0
0x140022561  xor     eax, eax
0x140022563  mov     [rsp+180h+var_140], 0
0x14002256b  xor     ecx, ecx
0x14002256d  mov     [rbp+80h+var_F0], rax
0x140022571  movups  [rsp+180h+var_110], xmm0
0x140022576  movups  [rbp+80h+var_100], xmm0
0x14002257a  call    SrvAdminInstanceGetFromType
0x14002257f  mov     rbx, rax
0x140022582  test    rax, rax
0x140022585  jnz     short loc_1400225CB
0x140022587  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002258e  lea     rax, WPP_GLOBAL_Control
0x140022595  cmp     rcx, rax
0x140022598  jz      loc_1400227A7
0x14002259e  mov     eax, [rcx+2Ch]
0x1400225a1  test    al, 20h
0x1400225a3  jz      loc_1400227A7
0x1400225a9  cmp     byte ptr [rcx+29h], 1
0x1400225ad  jb      loc_1400227A7
0x1400225b3  mov     rcx, [rcx+18h]
0x1400225b7  lea     edx, [rbx+1Fh]
0x1400225ba  lea     r8, WPP_f985cb20fdcf3c2b53247ccaba227cdb_Traceguids
0x1400225c1  call    WPP_SF_
0x1400225c6  jmp     loc_1400227A7
0x1400225cb  lea     r14, [rax+0C8h]
0x1400225d2  mov     dl, 1; Wait
0x1400225d4  mov     rcx, r14; Resource
0x1400225d7  call    cs:__imp_ExAcquireResourceSharedLite
0x1400225de  nop     dword ptr [rax+rax+00h]
0x1400225e3  mov     dl, 1; Wait
0x1400225e5  lea     rcx, [rbx+60h]; Resource
0x1400225e9  call    cs:__imp_ExAcquireResourceSharedLite
0x1400225f0  nop     dword ptr [rax+rax+00h]
0x1400225f5  xor     eax, eax
0x1400225f7  lea     r12, [rbx+198h]
0x1400225fe  xorps   xmm0, xmm0
0x140022601  mov     [rbp+80h+var_F0], rax
0x140022605  lea     rax, [rsp+180h+var_110]
0x14002260a  mov     [rsp+180h+Buffer], rax
0x14002260f  movups  [rsp+180h+var_110], xmm0
0x140022614  movups  [rbp+80h+var_100], xmm0
0x140022618  jmp     loc_140022746
0x14002261d  mov     ecx, cs:dword_140036120
0x140022623  mov     rdi, [rsi+20h]
0x140022627  cmp     ecx, 5
0x14002262a  jbe     loc_140022729
0x140022630  call    _tlgKeywordOn
0x140022635  test    al, al
0x140022637  jz      loc_140022729
0x14002263d  mov     eax, [rdi+78h]
0x140022640  lea     rdx, word_140031B3A; int
0x140022647  mov     [rsp+180h+var_13C], eax
0x14002264b  lea     rax, [rsp+180h+var_13C]
0x140022650  mov     [rbp+80h+var_C0], rax
0x140022654  mov     eax, [rdi+70h]
0x140022657  mov     [rsp+180h+var_138], eax
0x14002265b  lea     rax, [rsp+180h+var_138]
0x140022660  mov     [rbp+80h+var_B0], rax
0x140022664  mov     eax, [rdi+7Ch]
0x140022667  mov     [rsp+180h+var_134], eax
0x14002266b  lea     rax, [rsp+180h+var_134]
0x140022670  mov     [rbp+80h+var_A0], rax
0x140022674  mov     eax, [rdi+80h]
0x14002267a  mov     [rsp+180h+var_130], eax
0x14002267e  lea     rax, [rsp+180h+var_130]
0x140022683  mov     [rbp+80h+var_90], rax
0x140022687  mov     eax, [rdi+84h]
0x14002268d  mov     [rsp+180h+var_12C], eax
0x140022691  lea     rax, [rsp+180h+var_12C]
0x140022696  mov     [rbp+80h+var_80], rax
0x14002269a  mov     eax, [rdi+88h]
0x1400226a0  mov     [rsp+180h+var_128], eax
0x1400226a4  lea     rax, [rsp+180h+var_128]
0x1400226a9  mov     [rbp+80h+var_70], rax
0x1400226ad  mov     eax, [rdi+8Ch]
0x1400226b3  mov     [rsp+180h+var_124], eax
0x1400226b7  lea     rax, [rsp+180h+var_124]
0x1400226bc  mov     [rbp+80h+var_60], rax
0x1400226c0  mov     eax, [rdi+94h]
0x1400226c6  mov     [rsp+180h+var_120], eax
0x1400226ca  lea     rax, [rsp+180h+var_120]
0x1400226cf  mov     [rbp+80h+var_50], rax
0x1400226d3  lea     rax, [rbp+80h+var_E0]
0x1400226d7  mov     [rsp+180h+DeleteCount], rax; __int64
0x1400226dc  mov     dword ptr [rsp+180h+RestartKey], 0Ah; ULONG
0x1400226e4  mov     [rbp+80h+var_B8], 4
0x1400226ec  mov     [rbp+80h+var_A8], 4
0x1400226f4  mov     [rbp+80h+var_98], 4
0x1400226fc  mov     [rbp+80h+var_88], 4
0x140022704  mov     [rbp+80h+var_78], 4
0x14002270c  mov     [rbp+80h+var_68], 4
0x140022714  mov     [rbp+80h+var_58], 4
0x14002271c  mov     [rbp+80h+var_48], 4
0x140022724  call    _tlgWriteTransfer_EtwWriteTransfer
0x140022729  mov     edx, [rdi+6Ch]
0x14002272c  lea     rcx, [rdi+70h]
0x140022730  call    InterlockedMinNoFence
0x140022735  mov     edx, [rdi+74h]
0x140022738  lea     rcx, [rdi+78h]
0x14002273c  call    InterlockedMinNoFence
0x140022741  mov     [rsp+180h+Buffer], rsi; Buffer
0x140022746  lea     rax, [rsp+180h+var_140]
0x14002274b  mov     r9d, 1; NextFlag
0x140022751  mov     [rsp+180h+DeleteCount], rax; DeleteCount
0x140022756  xor     r8d, r8d; MatchData
0x140022759  lea     rax, [rsp+180h+var_118]
0x14002275e  xor     edx, edx; MatchFunction
0x140022760  mov     rcx, r12; Table
0x140022763  mov     [rsp+180h+RestartKey], rax; RestartKey
0x140022768  call    cs:__imp_RtlEnumerateGenericTableLikeADirectory
0x14002276f  nop     dword ptr [rax+rax+00h]
0x140022774  mov     rsi, rax
0x140022777  test    rax, rax
0x14002277a  jnz     loc_14002261D
0x140022780  lea     rcx, [rbx+60h]; Resource
0x140022784  call    cs:__imp_ExReleaseResourceLite
0x14002278b  nop     dword ptr [rax+rax+00h]
0x140022790  mov     rcx, r14; Resource
0x140022793  call    cs:__imp_ExReleaseResourceLite
0x14002279a  nop     dword ptr [rax+rax+00h]
0x14002279f  mov     rcx, rbx
0x1400227a2  call    SrvAdminDereferenceInstance
0x1400227a7  mov     rcx, [rbp+80h+var_40]
0x1400227ab  xor     rcx, rsp; StackCookie
0x1400227ae  call    __security_check_cookie
0x1400227b3  add     rsp, 150h
0x1400227ba  pop     r15
0x1400227bc  pop     r14
0x1400227be  pop     r12
0x1400227c0  pop     rdi
0x1400227c1  pop     rsi
0x1400227c2  pop     rbx
0x1400227c3  pop     rbp
0x1400227c4  retn
```
