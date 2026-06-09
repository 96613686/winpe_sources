# LCompleteTransfer

- ea: `0x180008500`
- end: `0x1800088fb`
- name: `LCompleteTransfer`
- size: `1019`
- prototype: `__int64 __fastcall(__int64, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180028100`

## callees

- `0x180003d8c`
- `0x180008500`
- `0x180017adc`
- `0x180019fcc`
- `0x18001c24c`
- `0x18001c3ec`
- `0x18002c8d4`
- `0x18003e15c`
- `0x18003e3b4`
- `0x180040010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180008692`
- `KERNEL32!HeapAlloc` at `0x180008692`

## pseudocode

```c
__int64 __fastcall LCompleteTransfer(__int64 a1, int *a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  int v5; // edi
  __int64 v6; // r13
  unsigned int v7; // r14d
  __int64 v8; // rdx
  __int64 v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // r14
  int v12; // ebx
  __int64 v13; // r13
  __int64 v14; // rcx
  __int64 v15; // rdx
  _QWORD *v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  unsigned int v21; // [rsp+74h] [rbp-94h] BYREF
  __int64 v22; // [rsp+78h] [rbp-90h] BYREF
  __int64 v23; // [rsp+80h] [rbp-88h] BYREF
  int v24; // [rsp+88h] [rbp-80h]
  __int64 v25; // [rsp+90h] [rbp-78h] BYREF
  __int64 v26; // [rsp+98h] [rbp-70h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v28; // [rsp+A8h] [rbp-60h]
  __int64 v29; // [rsp+B0h] [rbp-58h]
  __int64 v30; // [rsp+B8h] [rbp-50h] BYREF
  __int64 (__fastcall *v31)(_QWORD, __int64, _QWORD, _QWORD, __int64, int); // [rsp+C0h] [rbp-48h] BYREF
  HANDLE lpTargetHandle; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v33; // [rsp+D0h] [rbp-38h]
  __int64 v34; // [rsp+D8h] [rbp-30h]
  __int64 v35; // [rsp+E0h] [rbp-28h]

  v3 = 0;
  lpTargetHandle = 0;
  v30 = 0;
  v31 = 0;
  v22 = 0;
  v25 = 0;
  v23 = 0;
  v5 = LineProlog(
         a1,
         1,
         a2[4],
         (int)&v30,
         4,
         &lpTargetHandle,
         (__int64)&v22 + 4,
         8,
         (__int64)&v31,
         (__int64)&v23,
         a2[2],
         (__int64)&v22,
         (__int64)&v25);
  if ( v5 > 0 )
  {
    v6 = 0;
    v26 = 0;
    v7 = 0;
    v21 = 0;
    v27 = 0;
    v8 = ReferenceObject(v4, (unsigned int)a2[5], 1229734723);
    v33 = v8;
    if ( !v8 )
    {
      v5 = -2147483615;
      goto LABEL_32;
    }
    if ( *(_QWORD *)(v8 + 8) != a1 )
    {
      v5 = -2147483615;
LABEL_31:
      v3 = 1;
      goto LABEL_32;
    }
    if ( *(_DWORD *)(v8 + 32) != 4 )
    {
      v5 = -2147483578;
      goto LABEL_31;
    }
    v4 = v25;
    v9 = *(_QWORD *)(v25 + 24);
    v29 = v9;
    v34 = v9;
    v28 = *(_QWORD *)(v8 + 24);
    v35 = v28;
    if ( v9 == v28 || (v4 = *(_QWORD *)(v25 + 16), *(_QWORD *)(v4 + 32) != *(_QWORD *)(*(_QWORD *)(v8 + 16) + 32LL)) )
    {
      v5 = -2147483624;
      v24 = -2147483624;
      v3 = 1;
      goto LABEL_32;
    }
    if ( a2[7] == 2 )
    {
      v10 = HeapAlloc(ghTapisrvHeap, 8u, 0x40u);
      v11 = v10;
      if ( !v10 )
      {
        v5 = -2147483580;
        goto LABEL_31;
      }
      *((_DWORD *)v10 + 1) = 5;
      *((_DWORD *)v10 + 2) = 1;
      v12 = SetCallConfList(v9, v10, 0);
      if ( !v12 )
      {
        v13 = v28;
        v12 = SetCallConfList(v28, v11, 0);
        if ( !v12 )
        {
          v12 = CreatetCallAndClient(*(_QWORD **)(v25 + 16), &v26, (__int64)&v27, 0, &v21);
          if ( !v12 )
          {
            v15 = v21;
            v16 = (_QWORD *)v23;
            *(_QWORD *)(v23 + 112) = v21;
            ReferenceObject(v14, v15, 1279345481);
            v6 = v26;
            *(_QWORD *)(v26 + 136) = v11;
            v11[3] = v6;
            v16[3] = *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v27 + 16) + 32LL) + 208LL);
            v16[10] = v6;
            v16[11] = (unsigned int)a2[6];
            v16[12] = v29;
            v16[13] = v28;
            v16[6] = LCompleteTransfer_PostProcess;
            v8 = v33;
            v7 = v21;
            goto LABEL_17;
          }
          SetCallConfList(v13, 0, 0);
        }
        SetCallConfList(v29, 0, 0);
      }
      ServerFree(v11);
      v5 = v12;
      goto LABEL_31;
    }
    if ( a2[7] != 1 )
    {
      v5 = -2147483585;
      goto LABEL_31;
    }
LABEL_17:
    *(_DWORD *)(v23 + 68) = a2[3];
    if ( v6 )
      v17 = v6 + 40;
    else
      v17 = 0;
    v18 = v31(*(unsigned int *)(v23 + 72), v30, *(_QWORD *)(*(_QWORD *)(v8 + 24) + 40LL), v7, v17, a2[7]);
    *a2 = v18;
    if ( v6 )
    {
      if ( v18 < 0 )
        v19 = 1;
      else
        v19 = 3;
      SetDrvCallFlags(v7, v19);
    }
    goto LABEL_31;
  }
LABEL_32:
  if ( v3 )
    DereferenceObject(v4, a2[5], 1);
  return LineEpilogAsync((_DWORD)a2, v5, (_DWORD)lpTargetHandle, HIDWORD(v22), v23, v22);
}

```

## disassembly

```asm
0x180008500  mov     r11, rsp
0x180008503  mov     [r11+18h], rbx
0x180008507  mov     [r11+20h], rdi
0x18000850b  mov     [r11+10h], rdx
0x18000850f  mov     [r11+8], rcx
0x180008513  push    r13
0x180008515  push    r14
0x180008517  push    r15
0x180008519  sub     rsp, 0F0h
0x180008520  mov     r15, rdx
0x180008523  mov     dword ptr [rsp+108h+var_90+4], 0
0x18000852b  xor     ebx, ebx
0x18000852d  mov     [r11-40h], rbx
0x180008531  mov     [r11-50h], rbx
0x180008535  mov     [r11-48h], rbx
0x180008539  mov     dword ptr [rsp+108h+var_90], ebx
0x18000853d  mov     [r11-78h], rbx
0x180008541  mov     [r11-88h], rbx
0x180008548  lea     rax, [r11-78h]
0x18000854c  mov     [rsp+108h+var_A8], rax; __int64
0x180008551  lea     rax, [rsp+108h+var_90]
0x180008556  mov     [rsp+108h+var_B0], rax; __int64
0x18000855b  mov     eax, [rdx+8]
0x18000855e  mov     [rsp+108h+var_B8], eax; int
0x180008562  lea     rax, [r11-88h]
0x180008569  mov     [rsp+108h+var_C0], rax; __int64
0x18000856e  lea     rax, [r11-48h]
0x180008572  mov     [rsp+108h+var_C8], rax; __int64
0x180008577  mov     [rsp+108h+var_D0], 8; int
0x18000857f  lea     rax, [rsp+108h+var_90+4]
0x180008584  mov     [rsp+108h+var_D8], rax; __int64
0x180008589  lea     rax, [r11-40h]
0x18000858d  mov     [rsp+108h+lpTargetHandle], rax; lpTargetHandle
0x180008592  mov     [rsp+108h+var_E8], 4; int
0x18000859a  lea     r9, [r11-50h]; int
0x18000859e  mov     r8d, [rdx+10h]; int
0x1800085a2  lea     edx, [rbx+1]; int
0x1800085a5  call    LineProlog
0x1800085aa  mov     edi, eax
0x1800085ac  test    eax, eax
0x1800085ae  jle     loc_1800088A2
0x1800085b4  xor     r13d, r13d
0x1800085b7  mov     [rsp+108h+var_70], r13
0x1800085bf  xor     r14d, r14d
0x1800085c2  mov     [rsp+108h+var_94], r14d
0x1800085c7  mov     [rsp+108h+var_68], rbx
0x1800085cf  mov     r8d, 494C4343h
0x1800085d5  mov     edx, [r15+14h]
0x1800085d9  call    ReferenceObject
0x1800085de  mov     rdx, rax
0x1800085e1  mov     [rsp+108h+var_38], rax
0x1800085e9  test    rax, rax
0x1800085ec  jnz     short loc_1800085F8
0x1800085ee  mov     edi, 80000021h
0x1800085f3  jmp     loc_1800088A2
0x1800085f8  mov     [rsp+108h+var_98], 1
0x180008600  mov     rax, [rsp+108h+arg_0]
0x180008608  cmp     [rdx+8], rax
0x18000860c  jz      short loc_180008618
0x18000860e  mov     edi, 80000021h
0x180008613  jmp     loc_18000889E
0x180008618  cmp     dword ptr [rdx+20h], 4
0x18000861c  jz      short loc_180008628
0x18000861e  mov     edi, 80000046h
0x180008623  jmp     loc_18000889E
0x180008628  mov     rcx, [rsp+108h+var_78]
0x180008630  mov     rbx, [rcx+18h]
0x180008634  mov     [rsp+108h+var_58], rbx
0x18000863c  mov     [rsp+108h+var_30], rbx
0x180008644  mov     rax, [rdx+18h]
0x180008648  mov     [rsp+108h+var_60], rax
0x180008650  mov     [rsp+108h+var_28], rax
0x180008658  cmp     rbx, rax
0x18000865b  jz      loc_180008872
0x180008661  mov     rax, [rdx+10h]
0x180008665  mov     rcx, [rcx+10h]
0x180008669  mov     rax, [rax+20h]
0x18000866d  cmp     [rcx+20h], rax
0x180008671  jnz     loc_180008872
0x180008677  cmp     dword ptr [r15+1Ch], 2
0x18000867c  jnz     loc_1800087F4
0x180008682  mov     edx, 8; dwFlags
0x180008687  lea     r8d, [rdx+38h]; dwBytes
0x18000868b  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180008692  call    cs:__imp_HeapAlloc
0x180008698  mov     r14, rax
0x18000869b  test    rax, rax
0x18000869e  jnz     short loc_1800086AA
0x1800086a0  mov     edi, 80000044h
0x1800086a5  jmp     loc_18000889E
0x1800086aa  mov     dword ptr [rax+4], 5
0x1800086b1  mov     dword ptr [rax+8], 1
0x1800086b8  xor     r8d, r8d
0x1800086bb  mov     rdx, r14
0x1800086be  mov     rcx, rbx
0x1800086c1  call    SetCallConfList
0x1800086c6  mov     ebx, eax
0x1800086c8  test    eax, eax
0x1800086ca  jnz     loc_1800087E5
0x1800086d0  xor     r8d, r8d
0x1800086d3  mov     rdx, r14
0x1800086d6  mov     r13, [rsp+108h+var_60]
0x1800086de  mov     rcx, r13
0x1800086e1  call    SetCallConfList
0x1800086e6  mov     ebx, eax
0x1800086e8  test    eax, eax
0x1800086ea  jnz     loc_1800087D3
0x1800086f0  lea     rax, [rsp+108h+var_94]
0x1800086f5  mov     qword ptr [rsp+108h+var_E8], rax
0x1800086fa  xor     r9d, r9d
0x1800086fd  lea     r8, [rsp+108h+var_68]
0x180008705  lea     rdx, [rsp+108h+var_70]
0x18000870d  mov     rcx, [rsp+108h+var_78]
0x180008715  mov     rcx, [rcx+10h]
0x180008719  call    CreatetCallAndClient
0x18000871e  mov     ebx, eax
0x180008720  test    eax, eax
0x180008722  jnz     loc_1800087C6
0x180008728  mov     edx, [rsp+108h+var_94]
0x18000872c  mov     rbx, [rsp+108h+var_88]
0x180008734  mov     [rbx+70h], rdx
0x180008738  mov     r8d, 4C414349h
0x18000873e  call    ReferenceObject
0x180008743  mov     r13, [rsp+108h+var_70]
0x18000874b  mov     [r13+88h], r14
0x180008752  mov     [r14+18h], r13
0x180008756  mov     rax, [rsp+108h+var_68]
0x18000875e  mov     rcx, [rax+10h]
0x180008762  mov     rax, [rcx+20h]
0x180008766  mov     ecx, [rax+0D0h]
0x18000876c  mov     [rbx+18h], rcx
0x180008770  mov     [rbx+50h], r13
0x180008774  mov     eax, [r15+18h]
0x180008778  mov     [rbx+58h], rax
0x18000877c  mov     rcx, [rsp+108h+var_58]
0x180008784  mov     [rbx+60h], rcx
0x180008788  mov     rax, [rsp+108h+var_60]
0x180008790  mov     [rbx+68h], rax
0x180008794  lea     rax, LCompleteTransfer_PostProcess
0x18000879b  mov     [rbx+30h], rax
0x18000879f  mov     rdx, [rsp+108h+var_38]
0x1800087a7  mov     r14d, [rsp+108h+var_94]
0x1800087ac  mov     ecx, [r15+0Ch]
0x1800087b0  mov     rax, [rsp+108h+var_88]
0x1800087b8  mov     [rax+44h], ecx
0x1800087bb  test    r13, r13
0x1800087be  jz      short loc_180008805
0x1800087c0  lea     rax, [r13+28h]
0x1800087c4  jmp     short loc_180008807
0x1800087c6  xor     r8d, r8d
0x1800087c9  xor     edx, edx
0x1800087cb  mov     rcx, r13
0x1800087ce  call    SetCallConfList
0x1800087d3  xor     r8d, r8d
0x1800087d6  xor     edx, edx
0x1800087d8  mov     rcx, [rsp+108h+var_58]
0x1800087e0  call    SetCallConfList
0x1800087e5  mov     rcx, r14; lpMem
0x1800087e8  call    ServerFree
0x1800087ed  mov     edi, ebx
0x1800087ef  jmp     loc_18000889E
0x1800087f4  cmp     dword ptr [r15+1Ch], 1
0x1800087f9  jz      short loc_1800087AC
0x1800087fb  mov     edi, 8000003Fh
0x180008800  jmp     loc_18000889E
0x180008805  xor     eax, eax
0x180008807  mov     r9d, r14d
0x18000880a  mov     r8, [rdx+18h]
0x18000880e  mov     ecx, [r15+1Ch]
0x180008812  mov     dword ptr [rsp+108h+lpTargetHandle], ecx
0x180008816  mov     qword ptr [rsp+108h+var_E8], rax
0x18000881b  mov     r8, [r8+28h]
0x18000881f  mov     rdx, [rsp+108h+var_50]
0x180008827  mov     rcx, [rsp+108h+var_88]
0x18000882f  mov     ecx, [rcx+48h]
0x180008832  mov     rax, [rsp+108h+var_48]
0x18000883a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000883f  mov     [r15], eax
0x180008842  test    r13, r13
0x180008845  jz      short loc_18000889E
0x180008847  test    eax, eax
0x180008849  js      short loc_180008863
0x18000884b  cmp     eax, 80000061h
0x180008850  jbe     short loc_18000885C
0x180008852  add     eax, 6FFFFFFFh
0x180008857  cmp     eax, 24h ; '$'
0x18000885a  ja      short loc_180008863
0x18000885c  mov     edx, 3
0x180008861  jmp     short loc_180008868
0x180008863  mov     edx, 1
0x180008868  mov     ecx, r14d
0x18000886b  call    SetDrvCallFlags
0x180008870  jmp     short loc_18000889E
0x180008872  mov     edi, 80000018h
0x180008877  mov     [rsp+108h+var_80], edi
0x18000887e  mov     ebx, [rsp+108h+var_98]
0x180008882  jmp     short loc_1800088A2
0x180008884  mov     edi, 80000018h
0x180008889  mov     [rsp+108h+var_80], edi
0x180008890  mov     r15, [rsp+108h+arg_8]
0x180008898  mov     ebx, [rsp+108h+var_98]
0x18000889c  jmp     short loc_1800088A2
0x18000889e  mov     ebx, [rsp+108h+var_98]
0x1800088a2  test    ebx, ebx
0x1800088a4  jz      short loc_1800088B5
0x1800088a6  mov     r8d, 1
0x1800088ac  mov     edx, [r15+14h]
0x1800088b0  call    DereferenceObject
0x1800088b5  mov     eax, dword ptr [rsp+108h+var_90]
0x1800088b9  mov     dword ptr [rsp+108h+lpTargetHandle], eax
0x1800088bd  mov     rax, [rsp+108h+var_88]
0x1800088c5  mov     qword ptr [rsp+108h+var_E8], rax
0x1800088ca  mov     r9d, dword ptr [rsp+108h+var_90+4]
0x1800088cf  mov     r8, [rsp+108h+var_40]
0x1800088d7  mov     edx, edi
0x1800088d9  mov     rcx, r15
0x1800088dc  call    LineEpilogAsync
0x1800088e1  lea     r11, [rsp+108h+var_18]
0x1800088e9  mov     rbx, [r11+30h]
0x1800088ed  mov     rdi, [r11+38h]
0x1800088f1  mov     rsp, r11
0x1800088f4  pop     r15
0x1800088f6  pop     r14
0x1800088f8  pop     r13
0x1800088fa  retn
```
