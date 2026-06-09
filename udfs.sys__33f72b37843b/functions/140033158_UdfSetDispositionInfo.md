# UdfSetDispositionInfo

- ea: `0x140033158`
- end: `0x1400333b4`
- name: `UdfSetDispositionInfo`
- size: `604`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140031f84`

## callees

- `0x14000ca54`
- `0x14000cad4`
- `0x140010c5c`
- `0x1400168d8`
- `0x140033158`

## import_xrefs

- `ntoskrnl!MmFlushImageSection` at `0x14003323f`
- `ntoskrnl!MmFlushImageSection` at `0x1400332ce`
- `ntoskrnl!MmFlushImageSection` at `0x14003323f`
- `ntoskrnl!MmFlushImageSection` at `0x1400332ce`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x1400333a3`
- `ntoskrnl!FsRtlNotifyFullChangeDirectory` at `0x1400333a3`

## pseudocode

```c
__int64 __fastcall UdfSetDispositionInfo(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  __int64 v8; // rsi
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rdx

  if ( !*(_QWORD *)(a4 + 16) )
    return 3221225761LL;
  v8 = *(_QWORD *)(a1 + 16);
  if ( a3 == *(_QWORD *)(v8 + 288) )
    return 3221225761LL;
  if ( !*a5 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
    {
      WPP_SF_qq(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        14,
        WPP_0dbe93714b6730a9f09221a306b03890_Traceguids,
        a3,
        *(_QWORD *)(a4 + 16));
    }
    *(_DWORD *)(*(_QWORD *)(a4 + 16) + 68LL) &= ~2u;
    *(_BYTE *)(a2 + 73) = 0;
    return 0;
  }
  if ( (*(_DWORD *)(a3 + 220) & 1) == 0 )
  {
    if ( *(_WORD *)a3 == 2355 )
    {
      if ( !(unsigned __int8)UdfDirectoryIsEmpty(a1, a3) )
        return 3221225729LL;
    }
    else if ( !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(a3 + 424) + 8LL), MmFlushForDelete) )
    {
      v10 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) == 0 )
      {
        return 3221225761LL;
      }
      v11 = 16;
      goto LABEL_20;
    }
    if ( (*(_DWORD *)(a3 + 212) & 0x18) == 0 )
    {
      v12 = *(__int64 **)(*(_QWORD *)(a3 + 136) + 32LL);
      while ( 1 )
      {
        v13 = *(_QWORD *)(a3 + 136);
        if ( v12 == (__int64 *)(v13 + 32) )
          break;
        if ( !*((_DWORD *)v12 + 20) )
        {
          v14 = v12[38];
          v12 = (__int64 *)*v12;
          if ( MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v14 + 8), MmFlushForDelete) )
            continue;
        }
        return 3221225761LL;
      }
      v15 = *(_QWORD *)(v13 + 24);
      if ( v15 )
      {
        v16 = (_QWORD *)(v15 + 536);
        v17 = (_QWORD *)*v16;
        if ( (_QWORD *)*v16 != v16 )
        {
          do
          {
            *((_DWORD *)v17 + 15) |= 2u;
            v17 = (_QWORD *)*v17;
          }
          while ( v17 != (_QWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 24LL) + 536LL) );
        }
      }
    }
    *(_BYTE *)(a2 + 73) = 1;
    *(_DWORD *)(*(_QWORD *)(a4 + 16) + 68LL) |= 2u;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) != 0 )
    {
      WPP_SF_q(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        17,
        WPP_0dbe93714b6730a9f09221a306b03890_Traceguids,
        *(_QWORD *)(a4 + 16));
    }
    if ( *(_WORD *)a3 == 2355 )
      FsRtlNotifyFullChangeDirectory(
        *(PNOTIFY_SYNC *)(v8 + 1712),
        (PLIST_ENTRY)(v8 + 1720),
        *(PVOID *)(a2 + 24),
        0,
        0,
        0,
        0,
        0,
        0,
        0);
    return 0;
  }
  v10 = *(_QWORD *)&WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x200) == 0 )
  {
    return 3221225761LL;
  }
  v11 = 15;
LABEL_20:
  WPP_SF_(*(_QWORD *)(v10 + 24), v11, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids);
  return 3221225761LL;
}

```

## disassembly

```asm
0x140033158  push    rbx
0x14003315a  push    rbp
0x14003315b  push    rsi
0x14003315c  push    rdi
0x14003315d  push    r12
0x14003315f  push    r14
0x140033161  sub     rsp, 58h
0x140033165  mov     rbx, r8
0x140033168  mov     rbp, r9
0x14003316b  mov     r8, [r9+10h]
0x14003316f  mov     r14, rdx
0x140033172  test    r8, r8
0x140033175  jz      loc_140033280
0x14003317b  mov     rsi, [rcx+10h]
0x14003317f  cmp     rbx, [rsi+120h]
0x140033186  jz      loc_140033280
0x14003318c  mov     rax, [rsp+88h+arg_20]
0x140033194  cmp     byte ptr [rax], 0
0x140033197  jnz     short loc_1400331E6
0x140033199  mov     rcx, cs:WPP_GLOBAL_Control
0x1400331a0  lea     rax, WPP_GLOBAL_Control
0x1400331a7  cmp     rcx, rax
0x1400331aa  jz      short loc_1400331D2
0x1400331ac  test    dword ptr [rcx+2Ch], 200h
0x1400331b3  jz      short loc_1400331D2
0x1400331b5  mov     rcx, [rcx+18h]
0x1400331b9  mov     edx, 0Eh
0x1400331be  mov     qword ptr [rsp+88h+WatchTree], r8
0x1400331c3  mov     r9, rbx
0x1400331c6  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x1400331cd  call    WPP_SF_qq
0x1400331d2  mov     rax, [rbp+10h]
0x1400331d6  and     dword ptr [rax+44h], 0FFFFFFFDh
0x1400331da  mov     byte ptr [r14+49h], 0
0x1400331df  xor     eax, eax
0x1400331e1  jmp     loc_140033285
0x1400331e6  mov     eax, [rbx+0DCh]
0x1400331ec  test    al, 1
0x1400331ee  jz      short loc_140033213
0x1400331f0  mov     rcx, cs:WPP_GLOBAL_Control; int
0x1400331f7  lea     rax, WPP_GLOBAL_Control
0x1400331fe  cmp     rcx, rax
0x140033201  jz      short loc_140033280
0x140033203  test    dword ptr [rcx+2Ch], 200h
0x14003320a  jz      short loc_140033280
0x14003320c  mov     edx, 0Fh
0x140033211  jmp     short loc_140033270
0x140033213  mov     r12d, 933h
0x140033219  cmp     r12w, [rbx]
0x14003321d  jnz     short loc_140033232
0x14003321f  mov     rdx, rbx; int
0x140033222  call    UdfDirectoryIsEmpty
0x140033227  test    al, al
0x140033229  jnz     short loc_140033293
0x14003322b  mov     eax, 0C0000101h
0x140033230  jmp     short loc_140033285
0x140033232  mov     rcx, [rbx+1A8h]
0x140033239  xor     edx, edx; FlushType
0x14003323b  add     rcx, 8; SectionObjectPointer
0x14003323f  call    cs:__imp_MmFlushImageSection
0x140033246  nop     dword ptr [rax+rax+00h]
0x14003324b  test    al, al
0x14003324d  jnz     short loc_140033293
0x14003324f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033256  lea     rax, WPP_GLOBAL_Control
0x14003325d  cmp     rcx, rax
0x140033260  jz      short loc_140033280
0x140033262  test    dword ptr [rcx+2Ch], 200h
0x140033269  jz      short loc_140033280
0x14003326b  mov     edx, 10h
0x140033270  mov     rcx, [rcx+18h]
0x140033274  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x14003327b  call    WPP_SF_
0x140033280  mov     eax, 0C0000121h
0x140033285  add     rsp, 58h
0x140033289  pop     r14
0x14003328b  pop     r12
0x14003328d  pop     rdi
0x14003328e  pop     rsi
0x14003328f  pop     rbp
0x140033290  pop     rbx
0x140033291  retn
0x140033293  mov     eax, [rbx+0D4h]
0x140033299  test    al, 18h
0x14003329b  jnz     short loc_140033315
0x14003329d  mov     rax, [rbx+88h]
0x1400332a4  mov     rdi, [rax+20h]
0x1400332a8  mov     rcx, [rbx+88h]
0x1400332af  lea     rax, [rcx+20h]
0x1400332b3  cmp     rdi, rax
0x1400332b6  jz      short loc_1400332E0
0x1400332b8  cmp     dword ptr [rdi+50h], 0
0x1400332bc  jnz     short loc_140033280
0x1400332be  mov     rcx, [rdi+130h]
0x1400332c5  xor     edx, edx; FlushType
0x1400332c7  mov     rdi, [rdi]
0x1400332ca  add     rcx, 8; SectionObjectPointer
0x1400332ce  call    cs:__imp_MmFlushImageSection
0x1400332d5  nop     dword ptr [rax+rax+00h]
0x1400332da  test    al, al
0x1400332dc  jnz     short loc_1400332A8
0x1400332de  jmp     short loc_140033280
0x1400332e0  mov     rax, [rcx+18h]
0x1400332e4  test    rax, rax
0x1400332e7  jz      short loc_140033315
0x1400332e9  add     rax, 218h
0x1400332ef  mov     rdx, [rax]
0x1400332f2  cmp     rdx, rax
0x1400332f5  jz      short loc_140033315
0x1400332f7  or      dword ptr [rdx+3Ch], 2
0x1400332fb  mov     rax, [rbx+88h]
0x140033302  mov     rdx, [rdx]
0x140033305  mov     rcx, [rax+18h]
0x140033309  add     rcx, 218h
0x140033310  cmp     rdx, rcx
0x140033313  jnz     short loc_1400332F7
0x140033315  mov     byte ptr [r14+49h], 1
0x14003331a  mov     rax, [rbp+10h]
0x14003331e  or      dword ptr [rax+44h], 2
0x140033322  mov     rcx, cs:WPP_GLOBAL_Control
0x140033329  lea     rax, WPP_GLOBAL_Control
0x140033330  cmp     rcx, rax
0x140033333  jz      short loc_140033357
0x140033335  test    dword ptr [rcx+2Ch], 200h
0x14003333c  jz      short loc_140033357
0x14003333e  mov     r9, [rbp+10h]
0x140033342  lea     r8, WPP_0dbe93714b6730a9f09221a306b03890_Traceguids
0x140033349  mov     rcx, [rcx+18h]
0x14003334d  mov     edx, 11h
0x140033352  call    WPP_SF_q
0x140033357  cmp     [rbx], r12w
0x14003335b  jnz     loc_1400331DF
0x140033361  mov     r8, [r14+18h]; FsContext
0x140033365  lea     rdx, [rsi+6B8h]; NotifyList
0x14003336c  mov     rcx, [rsi+6B0h]; NotifySync
0x140033373  xor     r9d, r9d; FullDirectoryName
0x140033376  mov     [rsp+88h+SubjectContext], 0; SubjectContext
0x14003337f  mov     [rsp+88h+TraverseCallback], 0; TraverseCallback
0x140033388  mov     [rsp+88h+NotifyIrp], 0; NotifyIrp
0x140033391  mov     [rsp+88h+CompletionFilter], 0; CompletionFilter
0x140033399  mov     [rsp+88h+IgnoreBuffer], 0; IgnoreBuffer
0x14003339e  mov     [rsp+88h+WatchTree], 0; WatchTree
0x1400333a3  call    cs:__imp_FsRtlNotifyFullChangeDirectory
0x1400333aa  nop     dword ptr [rax+rax+00h]
0x1400333af  jmp     loc_1400331DF
```
