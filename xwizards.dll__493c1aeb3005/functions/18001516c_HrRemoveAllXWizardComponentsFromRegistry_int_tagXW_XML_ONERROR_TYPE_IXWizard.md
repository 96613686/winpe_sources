# HrRemoveAllXWizardComponentsFromRegistry(int,tagXW_XML_ONERROR_TYPE,IXWizard *)

- ea: `0x18001516c`
- end: `0x18001561b`
- name: `?HrRemoveAllXWizardComponentsFromRegistry@@YAJHW4tagXW_XML_ONERROR_TYPE@@PEAUIXWizard@@@Z`
- size: `1199`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009d20`
- `0x180014248`

## callees

- `0x18000ae04`
- `0x18000c77c`
- `0x18001516c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001531a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800155d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001531a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800153f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800154d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800155d6`

## pseudocode

```c
__int64 __fastcall HrRemoveAllXWizardComponentsFromRegistry(unsigned int a1, int a2, __int64 *a3)
{
  __int64 *v3; // rdi
  int WizardComponentCount; // eax
  unsigned int v5; // ebx
  _QWORD *v7; // r12
  unsigned int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  int v11; // eax
  int v12; // edi
  __int64 v13; // rsi
  int v14; // eax
  int v15; // esi
  __int64 v16; // rbx
  int v17; // eax
  __int64 v18; // r12
  _QWORD *v19; // rsi
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r9
  unsigned int v24; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-34h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-30h]
  __int64 v27; // [rsp+40h] [rbp-28h] BYREF
  __int64 v28; // [rsp+48h] [rbp-20h] BYREF
  _QWORD *v29; // [rsp+50h] [rbp-18h]
  unsigned int v33; // [rsp+C8h] [rbp+60h] BYREF

  v3 = a3;
  v25 = 0;
  v24 = 0;
  v33 = 0;
  WizardComponentCount = HrGetWizardComponentCount(0, 0, &v25);
  v5 = WizardComponentCount;
  if ( WizardComponentCount >= 0 )
  {
    if ( v25 )
    {
      v29 = CoTaskMemAlloc(8LL * v25);
      v7 = v29;
      if ( v29 )
      {
        v8 = v25;
        v9 = 0;
        v24 = v25;
        while ( 1 )
        {
          v26 = v8;
          v10 = *v3;
          v27 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v10 + 104))(v3, 0, &v27);
          v12 = v11;
          if ( v11 < 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_77;
            v22 = 21;
LABEL_75:
            v23 = (unsigned int)v11;
            goto LABEL_76;
          }
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, unsigned int *))(*(_QWORD *)v27 + 24LL))(
                  v27,
                  v24,
                  v7,
                  &v33);
          if ( v12 >= 0 && v33 )
          {
            v13 = 0;
            do
            {
              if ( v12 >= 0 )
              {
                v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*a3 + 56))(a3, v7[v13], a1);
                v12 = v14;
                if ( v14 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      20,
                      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
                      (unsigned int)v14);
                  if ( a2 == 2 )
                  {
                    v9 = 1;
                    v12 = 0;
                  }
                }
              }
              CoTaskMemFree((LPVOID)v7[v13]);
              v13 = (unsigned int)(v13 + 1);
            }
            while ( (unsigned int)v13 < v33 );
          }
          v15 = v9;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
          if ( v12 < 0 )
            goto LABEL_77;
          v28 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 *))(*a3 + 112))(a3, 0, 0, &v28);
          v12 = v11;
          if ( v11 < 0 )
            break;
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, unsigned int *))(*(_QWORD *)v28 + 24LL))(
                  v28,
                  v24,
                  v7,
                  &v33);
          if ( v12 >= 0 && v33 )
          {
            v16 = 0;
            do
            {
              if ( v12 >= 0 )
              {
                v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*a3 + 64))(a3, v7[v16], a1);
                v12 = v17;
                if ( v17 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      22,
                      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
                      (unsigned int)v17);
                  if ( a2 == 2 )
                  {
                    v15 = 1;
                    v12 = 0;
                  }
                }
              }
              CoTaskMemFree((LPVOID)v7[v16]);
              v16 = (unsigned int)(v16 + 1);
            }
            while ( (unsigned int)v16 < v33 );
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          v9 = v15;
          if ( v12 < 0 )
            goto LABEL_77;
          v28 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64 *))(*a3 + 152))(a3, 0, 0, &v28);
          v12 = v11;
          if ( v11 < 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v22 = 25;
              goto LABEL_75;
            }
            goto LABEL_77;
          }
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *, unsigned int *))(*(_QWORD *)v28 + 24LL))(
                  v28,
                  v24,
                  v7,
                  &v33);
          if ( v12 >= 0 && v33 )
          {
            v18 = 0;
            v19 = v29;
            do
            {
              if ( v12 >= 0 )
              {
                v20 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*a3 + 72))(a3, v19[v18], a1);
                v12 = v20;
                if ( v20 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      24,
                      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
                      (unsigned int)v20);
                  if ( a2 == 2 )
                  {
                    v9 = 1;
                    v12 = 0;
                  }
                }
              }
              CoTaskMemFree((LPVOID)v19[v18]);
              v18 = (unsigned int)(v18 + 1);
            }
            while ( (unsigned int)v18 < v33 );
            v7 = v19;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( v12 < 0 )
            goto LABEL_77;
          v11 = HrGetWizardComponentCount(0, 0, &v24);
          v12 = v11;
          if ( v11 < 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              v22 = 26;
              goto LABEL_75;
            }
            goto LABEL_77;
          }
          v8 = v24;
          if ( !v24 || v26 == v24 )
          {
            if ( v24 <= v25 )
              goto LABEL_77;
LABEL_60:
            v12 = -2147418113;
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
              goto LABEL_77;
            v22 = 27;
            v23 = 2147549183LL;
LABEL_76:
            WPP_SF_d(v21[2], v22, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v23);
            goto LABEL_77;
          }
          if ( v24 > v25 )
            goto LABEL_60;
          v3 = a3;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v22 = 23;
          goto LABEL_75;
        }
LABEL_77:
        CoTaskMemFree(v7);
        if ( v9 )
          v12 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            28,
            &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
            (unsigned int)v12);
        return (unsigned int)v12;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
            2147942414LL);
        return 2147942414LL;
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)WizardComponentCount);
    return v5;
  }
}

```

## disassembly

```asm
0x18001516c  mov     [rsp-40h+arg_10], r8
0x180015171  mov     [rsp-40h+arg_8], edx
0x180015175  mov     [rsp-40h+arg_0], ecx
0x180015179  push    rbp
0x18001517a  push    rbx
0x18001517b  push    rsi
0x18001517c  push    rdi
0x18001517d  push    r12
0x18001517f  push    r13
0x180015181  push    r14
0x180015183  push    r15
0x180015185  mov     rbp, rsp
0x180015188  sub     rsp, 68h
0x18001518c  xor     r14d, r14d
0x18001518f  mov     rdi, r8
0x180015192  lea     r8, [rbp+var_34]
0x180015196  mov     [rbp+var_34], r14d
0x18001519a  xor     edx, edx
0x18001519c  mov     [rbp+var_38], r14d
0x1800151a0  xor     ecx, ecx
0x1800151a2  mov     [rbp+arg_18], r14d
0x1800151a6  call    ?HrGetWizardComponentCount@@YAJQEAGW4tagXW_COMPONENT_HIERARCHY@@PEAK@Z; HrGetWizardComponentCount(ushort * const,tagXW_COMPONENT_HIERARCHY,ulong *)
0x1800151ab  mov     ebx, eax
0x1800151ad  test    eax, eax
0x1800151af  jns     short loc_1800151E9
0x1800151b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151b8  lea     r14, WPP_GLOBAL_Control
0x1800151bf  cmp     rcx, r14
0x1800151c2  jz      short loc_1800151E2
0x1800151c4  test    byte ptr [rcx+1Ch], 4
0x1800151c8  jz      short loc_1800151E2
0x1800151ca  mov     rcx, [rcx+10h]
0x1800151ce  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800151d5  mov     edx, 12h
0x1800151da  mov     r9d, eax
0x1800151dd  call    WPP_SF_d
0x1800151e2  mov     eax, ebx
0x1800151e4  jmp     loc_18001560A
0x1800151e9  mov     eax, [rbp+var_34]
0x1800151ec  test    eax, eax
0x1800151ee  jnz     short loc_1800151FA
0x1800151f0  mov     eax, 1
0x1800151f5  jmp     loc_18001560A
0x1800151fa  mov     rcx, rax
0x1800151fd  shl     rcx, 3; cb
0x180015201  call    cs:__imp_CoTaskMemAlloc
0x180015207  mov     [rbp+var_18], rax
0x18001520b  mov     r12, rax
0x18001520e  test    rax, rax
0x180015211  jnz     short loc_18001524F
0x180015213  mov     rcx, cs:WPP_GLOBAL_Control
0x18001521a  lea     r14, WPP_GLOBAL_Control
0x180015221  cmp     rcx, r14
0x180015224  jz      short loc_180015245
0x180015226  test    byte ptr [rcx+1Ch], 4
0x18001522a  jz      short loc_180015245
0x18001522c  mov     rcx, [rcx+10h]
0x180015230  lea     edx, [rax+13h]
0x180015233  mov     r9d, 8007000Eh
0x180015239  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180015240  call    WPP_SF_d
0x180015245  mov     eax, 8007000Eh
0x18001524a  jmp     loc_18001560A
0x18001524f  mov     eax, [rbp+var_34]
0x180015252  lea     r15, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180015259  mov     ebx, r14d
0x18001525c  mov     [rbp+var_38], eax
0x18001525f  lea     r14, WPP_GLOBAL_Control
0x180015266  mov     r13d, 1
0x18001526c  mov     [rbp+var_30], eax
0x18001526f  lea     r8, [rbp+var_28]
0x180015273  mov     rax, [rdi]
0x180015276  xor     edx, edx
0x180015278  mov     rcx, rdi
0x18001527b  mov     [rbp+var_28], 0
0x180015283  mov     rax, [rax+68h]
0x180015287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001528c  mov     edi, eax
0x18001528e  test    eax, eax
0x180015290  js      loc_1800155AD
0x180015296  mov     rcx, [rbp+var_28]
0x18001529a  lea     r9, [rbp+arg_18]
0x18001529e  mov     edx, [rbp+var_38]
0x1800152a1  mov     r8, r12
0x1800152a4  mov     rax, [rcx]
0x1800152a7  mov     rax, [rax+18h]
0x1800152ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152b0  mov     edi, eax
0x1800152b2  test    eax, eax
0x1800152b4  js      short loc_180015328
0x1800152b6  mov     eax, [rbp+arg_18]
0x1800152b9  test    eax, eax
0x1800152bb  jz      short loc_180015328
0x1800152bd  xor     esi, esi
0x1800152bf  test    eax, eax
0x1800152c1  jz      short loc_180015328
0x1800152c3  test    edi, edi
0x1800152c5  js      short loc_180015316
0x1800152c7  mov     rcx, [rbp+arg_10]
0x1800152cb  mov     r8d, [rbp+arg_0]
0x1800152cf  mov     rdx, [r12+rsi*8]
0x1800152d3  mov     rax, [rcx]
0x1800152d6  mov     rax, [rax+38h]
0x1800152da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152df  mov     edi, eax
0x1800152e1  test    eax, eax
0x1800152e3  jns     short loc_180015316
0x1800152e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800152ec  cmp     rcx, r14
0x1800152ef  jz      short loc_18001530B
0x1800152f1  test    byte ptr [rcx+1Ch], 10h
0x1800152f5  jz      short loc_18001530B
0x1800152f7  mov     rcx, [rcx+10h]
0x1800152fb  mov     edx, 14h
0x180015300  mov     r9d, eax
0x180015303  mov     r8, r15
0x180015306  call    WPP_SF_d
0x18001530b  cmp     [rbp+arg_8], 2
0x18001530f  jnz     short loc_180015316
0x180015311  mov     ebx, r13d
0x180015314  xor     edi, edi
0x180015316  mov     rcx, [r12+rsi*8]; pv
0x18001531a  call    cs:__imp_CoTaskMemFree
0x180015320  add     esi, r13d
0x180015323  cmp     esi, [rbp+arg_18]
0x180015326  jb      short loc_1800152C3
0x180015328  mov     rcx, [rbp+var_28]
0x18001532c  mov     esi, ebx
0x18001532e  mov     rax, [rcx]
0x180015331  mov     rax, [rax+10h]
0x180015335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001533a  test    edi, edi
0x18001533c  js      loc_1800155D3
0x180015342  mov     rcx, [rbp+arg_10]
0x180015346  lea     r9, [rbp+var_20]
0x18001534a  xor     r8d, r8d
0x18001534d  mov     [rbp+var_20], 0
0x180015355  xor     edx, edx
0x180015357  mov     rax, [rcx]
0x18001535a  mov     rax, [rax+70h]
0x18001535e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015363  mov     edi, eax
0x180015365  test    eax, eax
0x180015367  js      loc_180015594
0x18001536d  mov     rcx, [rbp+var_20]
0x180015371  lea     r9, [rbp+arg_18]
0x180015375  mov     edx, [rbp+var_38]
0x180015378  mov     r8, r12
0x18001537b  mov     rax, [rcx]
0x18001537e  mov     rax, [rax+18h]
0x180015382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015387  mov     edi, eax
0x180015389  test    eax, eax
0x18001538b  js      short loc_1800153FF
0x18001538d  mov     eax, [rbp+arg_18]
0x180015390  test    eax, eax
0x180015392  jz      short loc_1800153FF
0x180015394  xor     ebx, ebx
0x180015396  test    eax, eax
0x180015398  jz      short loc_1800153FF
0x18001539a  test    edi, edi
0x18001539c  js      short loc_1800153ED
0x18001539e  mov     rcx, [rbp+arg_10]
0x1800153a2  mov     r8d, [rbp+arg_0]
0x1800153a6  mov     rdx, [r12+rbx*8]
0x1800153aa  mov     rax, [rcx]
0x1800153ad  mov     rax, [rax+40h]
0x1800153b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153b6  mov     edi, eax
0x1800153b8  test    eax, eax
0x1800153ba  jns     short loc_1800153ED
0x1800153bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800153c3  cmp     rcx, r14
0x1800153c6  jz      short loc_1800153E2
0x1800153c8  test    byte ptr [rcx+1Ch], 10h
0x1800153cc  jz      short loc_1800153E2
0x1800153ce  mov     rcx, [rcx+10h]
0x1800153d2  mov     edx, 16h
0x1800153d7  mov     r9d, eax
0x1800153da  mov     r8, r15
0x1800153dd  call    WPP_SF_d
0x1800153e2  cmp     [rbp+arg_8], 2
0x1800153e6  jnz     short loc_1800153ED
0x1800153e8  mov     esi, r13d
0x1800153eb  xor     edi, edi
0x1800153ed  mov     rcx, [r12+rbx*8]; pv
0x1800153f1  call    cs:__imp_CoTaskMemFree
0x1800153f7  add     ebx, r13d
0x1800153fa  cmp     ebx, [rbp+arg_18]
0x1800153fd  jb      short loc_18001539A
0x1800153ff  mov     rcx, [rbp+var_20]
0x180015403  mov     rax, [rcx]
0x180015406  mov     rax, [rax+10h]
0x18001540a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001540f  mov     ebx, esi
0x180015411  test    edi, edi
0x180015413  js      loc_1800155D3
0x180015419  mov     rcx, [rbp+arg_10]
0x18001541d  lea     r9, [rbp+var_20]
0x180015421  xor     r8d, r8d
0x180015424  mov     [rbp+var_20], 0
0x18001542c  xor     edx, edx
0x18001542e  mov     rax, [rcx]
0x180015431  mov     rax, [rax+98h]
0x180015438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001543d  mov     edi, eax
0x18001543f  test    eax, eax
0x180015441  js      loc_18001557B
0x180015447  mov     rcx, [rbp+var_20]
0x18001544b  lea     r9, [rbp+arg_18]
0x18001544f  mov     edx, [rbp+var_38]
0x180015452  mov     r8, r12
0x180015455  mov     rax, [rcx]
0x180015458  mov     rax, [rax+18h]
0x18001545c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015461  mov     edi, eax
0x180015463  test    eax, eax
0x180015465  js      loc_1800154EC
0x18001546b  mov     eax, [rbp+arg_18]
0x18001546e  test    eax, eax
0x180015470  jz      short loc_1800154EC
0x180015472  xor     r12d, r12d
0x180015475  test    eax, eax
0x180015477  jz      short loc_1800154E8
0x180015479  mov     rsi, [rbp+var_18]
0x18001547d  test    edi, edi
0x18001547f  js      short loc_1800154D0
0x180015481  mov     rcx, [rbp+arg_10]
0x180015485  mov     r8d, [rbp+arg_0]
0x180015489  mov     rdx, [rsi+r12*8]
0x18001548d  mov     rax, [rcx]
0x180015490  mov     rax, [rax+48h]
0x180015494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015499  mov     edi, eax
0x18001549b  test    eax, eax
0x18001549d  jns     short loc_1800154D0
0x18001549f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800154a6  cmp     rcx, r14
0x1800154a9  jz      short loc_1800154C5
0x1800154ab  test    byte ptr [rcx+1Ch], 10h
0x1800154af  jz      short loc_1800154C5
0x1800154b1  mov     rcx, [rcx+10h]
0x1800154b5  mov     edx, 18h
0x1800154ba  mov     r9d, eax
0x1800154bd  mov     r8, r15
0x1800154c0  call    WPP_SF_d
0x1800154c5  cmp     [rbp+arg_8], 2
0x1800154c9  jnz     short loc_1800154D0
0x1800154cb  mov     ebx, r13d
0x1800154ce  xor     edi, edi
0x1800154d0  mov     rcx, [rsi+r12*8]; pv
0x1800154d4  call    cs:__imp_CoTaskMemFree
0x1800154da  add     r12d, r13d
0x1800154dd  cmp     r12d, [rbp+arg_18]
0x1800154e1  jb      short loc_18001547D
0x1800154e3  mov     r12, rsi
0x1800154e6  jmp     short loc_1800154EC
0x1800154e8  mov     r12, [rbp+var_18]
0x1800154ec  mov     rcx, [rbp+var_20]
0x1800154f0  mov     rax, [rcx]
0x1800154f3  mov     rax, [rax+10h]
0x1800154f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154fc  test    edi, edi
0x1800154fe  js      loc_1800155D3
0x180015504  lea     r8, [rbp+var_38]
0x180015508  xor     edx, edx
0x18001550a  xor     ecx, ecx
0x18001550c  call    ?HrGetWizardComponentCount@@YAJQEAGW4tagXW_COMPONENT_HIERARCHY@@PEAK@Z; HrGetWizardComponentCount(ushort * const,tagXW_COMPONENT_HIERARCHY,ulong *)
0x180015511  mov     edi, eax
0x180015513  test    eax, eax
0x180015515  js      short loc_180015562
0x180015517  mov     eax, [rbp+var_38]
0x18001551a  test    eax, eax
0x18001551c  jz      short loc_180015531
0x18001551e  cmp     [rbp+var_30], eax
0x180015521  jz      short loc_180015531
0x180015523  cmp     eax, [rbp+var_34]
0x180015526  ja      short loc_18001553A
0x180015528  mov     rdi, [rbp+arg_10]
0x18001552c  jmp     loc_18001526C
0x180015531  cmp     eax, [rbp+var_34]
0x180015534  jbe     loc_1800155D3
0x18001553a  mov     edi, 8000FFFFh
0x18001553f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015546  cmp     rcx, r14
0x180015549  jz      loc_1800155D3
0x18001554f  test    byte ptr [rcx+1Ch], 4
0x180015553  jz      short loc_1800155D3
0x180015555  mov     edx, 1Bh
0x18001555a  mov     r9d, 8000FFFFh
0x180015560  jmp     short loc_1800155C7
0x180015562  mov     rcx, cs:WPP_GLOBAL_Control
0x180015569  cmp     rcx, r14
0x18001556c  jz      short loc_1800155D3
0x18001556e  test    byte ptr [rcx+1Ch], 4
0x180015572  jz      short loc_1800155D3
0x180015574  mov     edx, 1Ah
0x180015579  jmp     short loc_1800155C4
0x18001557b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015582  cmp     rcx, r14
  ... truncated ...
```
