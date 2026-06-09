# BuildMSOSCompatibleIDs

- ea: `0x14002231c`
- end: `0x140022498`
- name: `BuildMSOSCompatibleIDs`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140024928`
- `0x14002bc38`

## callees

- `0x14002231c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14002237a`
- `ntoskrnl!ExAllocatePool2` at `0x14002237a`

## string_xrefs

- `0x1400223b9`: `USB\MS_COMP_`
- `0x140022439`: `USB\MS_COMP_`
- `0x1400223ed`: `&MS_SUBCOMP_`

## pseudocode

```c
__int64 __fastcall BuildMSOSCompatibleIDs(_BYTE *a1, _BYTE *a2, int a3, _DWORD *a4)
{
  __int64 v4; // r11
  _WORD *v5; // r10
  __int64 Pool2; // rax
  __int64 v10; // r10
  __int64 v11; // rcx
  _WORD *v12; // r10
  __int64 v13; // rcx
  __int64 v14; // rcx

  v4 = 0;
  LODWORD(v5) = 0;
  if ( a2 && *a2 )
  {
    if ( a1 && *a1 )
    {
      a3 += 82;
LABEL_8:
      a3 += 42;
    }
  }
  else if ( a1 && *a1 )
  {
    goto LABEL_8;
  }
  if ( a3 )
  {
    Pool2 = ExAllocatePool2(256, (unsigned int)(a3 + 2), 1130525525);
    v4 = Pool2;
    v5 = (_WORD *)Pool2;
    if ( Pool2 )
    {
      if ( a2 && *a2 )
      {
        if ( !a1 || !*a1 )
          goto LABEL_28;
        v10 = Pool2 + 24;
        v11 = 0;
        *(_OWORD *)Pool2 = *(_OWORD *)L"USB\\MS_COMP_";
        *(_QWORD *)(Pool2 + 16) = *(_QWORD *)L"OMP_";
        do
        {
          if ( !a1[v11] )
            break;
          *(_WORD *)v10 = (char)a1[v11];
          v11 = (unsigned int)(v11 + 1);
          v10 += 2;
        }
        while ( (unsigned int)v11 < 8 );
        *(_OWORD *)v10 = *(_OWORD *)L"&MS_SUBCOMP_";
        *(_QWORD *)(v10 + 16) = *(_QWORD *)L"OMP_";
        v12 = (_WORD *)(v10 + 24);
        v13 = 0;
        do
        {
          if ( !a2[v13] )
            break;
          *v12 = (char)a2[v13];
          v13 = (unsigned int)(v13 + 1);
          ++v12;
        }
        while ( (unsigned int)v13 < 8 );
        *v12 = 0;
        v5 = v12 + 1;
      }
      else if ( !a1 )
      {
        goto LABEL_28;
      }
      if ( *a1 )
      {
        *(_OWORD *)v5 = *(_OWORD *)L"USB\\MS_COMP_";
        *((_QWORD *)v5 + 2) = *(_QWORD *)L"OMP_";
        v5 += 12;
        v14 = 0;
        do
        {
          if ( !a1[v14] )
            break;
          *v5 = (char)a1[v14];
          v14 = (unsigned int)(v14 + 1);
          ++v5;
        }
        while ( (unsigned int)v14 < 8 );
        *v5 = 0;
        LODWORD(v5) = (_DWORD)v5 + 2;
      }
    }
  }
LABEL_28:
  if ( a4 )
    *a4 = (_DWORD)v5 - v4;
  return v4;
}

```

## disassembly

```asm
0x14002231c  mov     [rsp+arg_0], rbx
0x140022321  mov     [rsp+arg_8], rsi
0x140022326  push    rdi
0x140022327  sub     rsp, 20h
0x14002232b  xor     r11d, r11d
0x14002232e  xor     r10d, r10d
0x140022331  mov     rsi, r9
0x140022334  mov     rdi, rdx
0x140022337  mov     rbx, rcx
0x14002233a  test    rdx, rdx
0x14002233d  jz      short loc_140022354
0x14002233f  cmp     [rdx], r10b
0x140022342  jz      short loc_140022354
0x140022344  test    rcx, rcx
0x140022347  jz      short loc_140022362
0x140022349  cmp     [rcx], r10b
0x14002234c  jz      short loc_140022362
0x14002234e  add     r8d, 52h ; 'R'
0x140022352  jmp     short loc_14002235E
0x140022354  test    rbx, rbx
0x140022357  jz      short loc_140022362
0x140022359  cmp     [rcx], r10b
0x14002235c  jz      short loc_140022362
0x14002235e  add     r8d, 2Ah ; '*'
0x140022362  test    r8d, r8d
0x140022365  jz      loc_140022479
0x14002236b  lea     edx, [r8+2]
0x14002236f  mov     ecx, 100h
0x140022374  mov     r8d, 43627355h
0x14002237a  call    cs:__imp_ExAllocatePool2
0x140022381  nop     dword ptr [rax+rax+00h]
0x140022386  mov     r11, rax
0x140022389  mov     r10, rax
0x14002238c  test    rax, rax
0x14002238f  jz      loc_140022479
0x140022395  test    rdi, rdi
0x140022398  jz      loc_14002242F
0x14002239e  cmp     byte ptr [rdi], 0
0x1400223a1  jz      loc_14002242F
0x1400223a7  test    rbx, rbx
0x1400223aa  jz      loc_140022479
0x1400223b0  cmp     byte ptr [rbx], 0
0x1400223b3  jz      loc_140022479
0x1400223b9  movups  xmm0, xmmword ptr cs:aUsbMsComp; "USB\\MS_COMP_"
0x1400223c0  lea     r10, [rax+18h]
0x1400223c4  xor     ecx, ecx
0x1400223c6  movups  xmmword ptr [rax], xmm0
0x1400223c9  movsd   xmm1, qword ptr cs:aUsbMsComp+10h; "OMP_"
0x1400223d1  movsd   qword ptr [rax+10h], xmm1
0x1400223d6  movsx   edx, byte ptr [rcx+rbx]
0x1400223da  test    dl, dl
0x1400223dc  jz      short loc_1400223ED
0x1400223de  mov     [r10], dx
0x1400223e2  inc     ecx
0x1400223e4  add     r10, 2
0x1400223e8  cmp     ecx, 8
0x1400223eb  jb      short loc_1400223D6
0x1400223ed  movups  xmm0, xmmword ptr cs:aMsSubcomp; "&MS_SUBCOMP_"
0x1400223f4  movups  xmmword ptr [r10], xmm0
0x1400223f8  movsd   xmm1, qword ptr cs:aMsSubcomp+10h; "OMP_"
0x140022400  movsd   qword ptr [r10+10h], xmm1
0x140022406  add     r10, 18h
0x14002240a  xor     ecx, ecx
0x14002240c  movsx   edx, byte ptr [rcx+rdi]
0x140022410  test    dl, dl
0x140022412  jz      short loc_140022423
0x140022414  mov     [r10], dx
0x140022418  inc     ecx
0x14002241a  add     r10, 2
0x14002241e  cmp     ecx, 8
0x140022421  jb      short loc_14002240C
0x140022423  xor     eax, eax
0x140022425  mov     [r10], ax
0x140022429  add     r10, 2
0x14002242d  jmp     short loc_140022434
0x14002242f  test    rbx, rbx
0x140022432  jz      short loc_140022479
0x140022434  cmp     byte ptr [rbx], 0
0x140022437  jz      short loc_140022479
0x140022439  movups  xmm0, xmmword ptr cs:aUsbMsComp; "USB\\MS_COMP_"
0x140022440  movups  xmmword ptr [r10], xmm0
0x140022444  movsd   xmm1, qword ptr cs:aUsbMsComp+10h; "OMP_"
0x14002244c  movsd   qword ptr [r10+10h], xmm1
0x140022452  add     r10, 18h
0x140022456  xor     ecx, ecx
0x140022458  movsx   edx, byte ptr [rcx+rbx]
0x14002245c  test    dl, dl
0x14002245e  jz      short loc_14002246F
0x140022460  mov     [r10], dx
0x140022464  inc     ecx
0x140022466  add     r10, 2
0x14002246a  cmp     ecx, 8
0x14002246d  jb      short loc_140022458
0x14002246f  xor     ecx, ecx
0x140022471  mov     [r10], cx
0x140022475  add     r10, 2
0x140022479  test    rsi, rsi
0x14002247c  jz      short loc_140022484
0x14002247e  sub     r10d, r11d
0x140022481  mov     [rsi], r10d
0x140022484  mov     rbx, [rsp+28h+arg_0]
0x140022489  mov     rax, r11
0x14002248c  mov     rsi, [rsp+28h+arg_8]
0x140022491  add     rsp, 20h
0x140022495  pop     rdi
0x140022496  retn
```
