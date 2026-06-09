# CWTask::CanRunTask(HWND__ * const,_GUID * const,tagXW_WIZARD_TYPE,ulong,ushort * const,ulong,IXWizardSource *,void * *)

- ea: `0x1800105a0`
- end: `0x180010a3b`
- name: `?CanRunTask@CWTask@@UEAAJQEAUHWND__@@QEAU_GUID@@W4tagXW_WIZARD_TYPE@@KQEAGKPEAUIXWizardSource@@PEAPEAX@Z`
- size: `1179`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002556`
- `0x18000addc`
- `0x18000ae04`
- `0x1800105a0`
- `0x18001bf44`
- `0x180032a02`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001093d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001093d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800109f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010710`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010710`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010702`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010702`

## pseudocode

```c
__int64 __fastcall CWTask::CanRunTask(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        int a7,
        __int64 (__fastcall ***a8)(_QWORD, GUID *),
        void **a9)
{
  __int64 (__fastcall ***v9)(_QWORD, GUID *); // r12
  __int64 v12; // rbp
  __int64 (__fastcall *v14)(__int64, _QWORD *); // rax
  unsigned int v15; // edi
  void *v16; // rax
  void *v17; // rbp
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  void *v21; // rbx
  HANDLE ProcessHeap; // rax
  PVOID *v23; // rcx
  int v24; // eax
  __int64 v25; // rcx
  int WrappedCOMComponent; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  __int64 v29; // r10
  unsigned int v30; // eax
  unsigned int v31; // esi
  unsigned int v32; // esi
  unsigned int v33; // esi
  unsigned int v34; // esi
  char *v35; // rax
  _DWORD *v36; // rbx
  HMODULE v37; // rcx
  void *Src; // [rsp+90h] [rbp+8h] BYREF
  __int64 v40; // [rsp+98h] [rbp+10h]

  v40 = a2;
  v9 = a8;
  Src = 0;
  v12 = a2;
  *a9 = 0;
  v14 = (__int64 (__fastcall *)(__int64, _QWORD *))a1[5];
  if ( !v14 )
    goto LABEL_33;
  v15 = v14(a2, a1 + 1);
  if ( !v15 )
  {
    if ( !Src || a4 != 1 && a4 != 2 && a4 != 32 && a4 != 512 && a4 != 1024 )
    {
      v23 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_23;
    }
    if ( (unsigned int)(*(_DWORD *)Src - 1) > 0x5F )
    {
      v17 = 0;
      v15 = -2147467261;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_19;
      v19 = 15;
      v20 = 2147500035LL;
    }
    else
    {
      v16 = CoTaskMemAlloc(0x60u);
      v17 = v16;
      if ( v16 )
      {
        memcpy_0(v16, Src, *(unsigned int *)Src);
LABEL_19:
        v21 = Src;
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v21);
        Src = v17;
        v12 = v40;
        goto LABEL_20;
      }
      v15 = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_19;
      v19 = 16;
      v20 = 2147942414LL;
    }
    WPP_SF_d(v18[2], v19, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids, v20);
    goto LABEL_19;
  }
LABEL_20:
  if ( v15 != -2147467263 )
  {
    v23 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
LABEL_33:
  v25 = a1[18];
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    a1[18] = 0;
  }
  WrappedCOMComponent = HrCreateWrappedCOMComponent(a1 + 1, a4, &IID_IXWizardTaskEvent, a1 + 18);
  v15 = WrappedCOMComponent;
  if ( WrappedCOMComponent < 0 )
  {
    if ( WrappedCOMComponent == -2147467263 )
    {
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_45;
      v27 = 17;
      v28 = 2147500033LL;
    }
    else
    {
      v23 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_45;
      v27 = 18;
      v28 = (unsigned int)WrappedCOMComponent;
    }
    WPP_SF_d(v23[2], v27, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids, v28);
  }
  v23 = (PVOID *)WPP_GLOBAL_Control;
LABEL_45:
  v29 = a1[18];
  if ( v29 )
  {
    v30 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD, int, __int64, int, __int64 (__fastcall ***)(_QWORD, GUID *), void **))(*(_QWORD *)v29 + 56LL))(
            v29,
            v12,
            a3,
            a4,
            a5,
            a6,
            a7,
            v9,
            &Src);
    v23 = (PVOID *)WPP_GLOBAL_Control;
    v15 = v30;
  }
  if ( v15 != -2147467263 )
  {
LABEL_22:
    if ( v15 )
      goto LABEL_29;
    goto LABEL_23;
  }
  v31 = a4 - 1;
  if ( v31 )
  {
    v32 = v31 - 1;
    if ( v32 )
    {
      v33 = v32 - 30;
      if ( v33 )
      {
        v34 = v33 - 480;
        if ( v34 )
        {
          if ( v34 != 512 )
            goto LABEL_29;
        }
      }
    }
  }
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 8) != 0 )
    WPP_SF_(v23[2], 19, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids);
  v35 = (char *)CoTaskMemAlloc(0x60u);
  v36 = v35;
  if ( !v35 )
  {
    v15 = -2147024882;
    v23 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids, 2147942414LL);
      v23 = (PVOID *)WPP_GLOBAL_Control;
    }
    goto LABEL_29;
  }
  memset_0(v35 + 4, 0, 0x5Cu);
  *v36 = 96;
  v37 = hModule;
  v36[1] |= 0x88004u;
  *((_QWORD *)v36 + 2) = v37;
  v15 = 0;
  *((_QWORD *)v36 + 9) = 7001;
  *((_QWORD *)v36 + 11) = 7000;
  *((_QWORD *)v36 + 3) = 10000;
  v23 = (PVOID *)WPP_GLOBAL_Control;
  Src = v36;
LABEL_23:
  if ( a1[19] )
    goto LABEL_29;
  v24 = (**v9)(v9, &IID_IXWizardTaskReport);
  v15 = v24;
  if ( v24 >= 0 )
    goto LABEL_28;
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids,
      (unsigned int)v24);
LABEL_28:
    v23 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( Src )
  {
    if ( v15 )
      CoTaskMemFree(Src);
    else
      *a9 = Src;
    v23 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 0x10) != 0 )
    WPP_SF_d(v23[2], 22, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x1800105a0  mov     r11, rsp
0x1800105a3  mov     [r11+18h], rbx
0x1800105a7  mov     [r11+10h], rdx
0x1800105ab  push    rbp
0x1800105ac  push    rsi
0x1800105ad  push    rdi
0x1800105ae  push    r12
0x1800105b0  push    r13
0x1800105b2  push    r14
0x1800105b4  push    r15
0x1800105b6  sub     rsp, 50h
0x1800105ba  mov     rax, [rsp+88h+arg_40]
0x1800105c2  lea     rbx, WPP_GLOBAL_Control
0x1800105c9  mov     r12, [rsp+88h+arg_38]
0x1800105d1  mov     esi, r9d
0x1800105d4  mov     r13, r8
0x1800105d7  mov     qword ptr [r11+8], 0
0x1800105df  mov     rbp, rdx
0x1800105e2  mov     r15, rcx
0x1800105e5  mov     qword ptr [rax], 0
0x1800105ec  mov     rax, [rcx+28h]
0x1800105f0  test    rax, rax
0x1800105f3  jz      loc_1800107DA
0x1800105f9  lea     rcx, [r11+8]
0x1800105fd  mov     [r11-50h], rcx
0x180010601  lea     rdx, [r15+8]
0x180010605  mov     ecx, [rsp+88h+arg_30]
0x18001060c  mov     [rsp+88h+var_58], ecx
0x180010610  mov     rcx, [rsp+88h+arg_28]
0x180010618  mov     [r11-60h], rcx
0x18001061c  mov     ecx, [rsp+88h+arg_20]
0x180010623  mov     [rsp+88h+var_68], ecx
0x180010627  mov     rcx, rbp
0x18001062a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001062f  mov     edi, eax
0x180010631  test    eax, eax
0x180010633  jnz     loc_180010726
0x180010639  cmp     [rsp+88h+Src], 0
0x180010642  jz      loc_1800107CE
0x180010648  mov     eax, esi
0x18001064a  sub     eax, 1
0x18001064d  jz      short loc_18001066B
0x18001064f  sub     eax, 1
0x180010652  jz      short loc_18001066B
0x180010654  sub     eax, 1Eh
0x180010657  jz      short loc_18001066B
0x180010659  sub     eax, 1E0h
0x18001065e  jz      short loc_18001066B
0x180010660  cmp     eax, 200h
0x180010665  jnz     loc_1800107CE
0x18001066b  mov     rax, [rsp+88h+Src]
0x180010673  mov     ecx, [rax]
0x180010675  dec     ecx
0x180010677  cmp     ecx, 5Fh ; '_'
0x18001067a  ja      short loc_1800106C8
0x18001067c  mov     ecx, 60h ; '`'; cb
0x180010681  call    cs:__imp_CoTaskMemAlloc
0x180010687  mov     rbp, rax
0x18001068a  test    rax, rax
0x18001068d  jz      short loc_1800106A4
0x18001068f  mov     rdx, [rsp+88h+Src]; Src
0x180010697  mov     rcx, rax; void *
0x18001069a  mov     r8d, [rdx]; Size
0x18001069d  call    memcpy_0
0x1800106a2  jmp     short loc_1800106FA
0x1800106a4  mov     edi, 8007000Eh
0x1800106a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106b0  cmp     rcx, rbx
0x1800106b3  jz      short loc_1800106FA
0x1800106b5  test    byte ptr [rcx+1Ch], 4
0x1800106b9  jz      short loc_1800106FA
0x1800106bb  mov     edx, 10h
0x1800106c0  mov     r9d, 8007000Eh
0x1800106c6  jmp     short loc_1800106EA
0x1800106c8  xor     ebp, ebp
0x1800106ca  mov     edi, 80004003h
0x1800106cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800106d6  cmp     rcx, rbx
0x1800106d9  jz      short loc_1800106FA
0x1800106db  test    byte ptr [rcx+1Ch], 8
0x1800106df  jz      short loc_1800106FA
0x1800106e1  lea     edx, [rbp+0Fh]
0x1800106e4  mov     r9d, 80004003h
0x1800106ea  mov     rcx, [rcx+10h]
0x1800106ee  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x1800106f5  call    WPP_SF_d
0x1800106fa  mov     rbx, [rsp+88h+Src]
0x180010702  call    cs:__imp_GetProcessHeap
0x180010708  mov     r8, rbx; lpMem
0x18001070b  xor     edx, edx; dwFlags
0x18001070d  mov     rcx, rax; hHeap
0x180010710  call    cs:__imp_HeapFree
0x180010716  mov     [rsp+88h+Src], rbp
0x18001071e  mov     rbp, [rsp+88h+arg_8]
0x180010726  cmp     edi, 80004001h
0x18001072c  jz      loc_1800107DA
0x180010732  mov     rcx, cs:WPP_GLOBAL_Control
0x180010739  test    edi, edi
0x18001073b  jnz     short loc_18001079E
0x18001073d  lea     rbx, WPP_GLOBAL_Control
0x180010744  lea     r8, [r15+98h]
0x18001074b  cmp     qword ptr [r8], 0
0x18001074f  jnz     short loc_18001079E
0x180010751  mov     rax, [r12]
0x180010755  lea     rdx, IID_IXWizardTaskReport
0x18001075c  mov     rcx, r12
0x18001075f  mov     rax, [rax]
0x180010762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010767  mov     edi, eax
0x180010769  test    eax, eax
0x18001076b  jns     short loc_180010797
0x18001076d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010774  cmp     rcx, rbx
0x180010777  jz      short loc_18001079E
0x180010779  test    byte ptr [rcx+1Ch], 4
0x18001077d  jz      short loc_18001079E
0x18001077f  mov     rcx, [rcx+10h]
0x180010783  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x18001078a  mov     edx, 15h
0x18001078f  mov     r9d, eax
0x180010792  call    WPP_SF_d
0x180010797  mov     rcx, cs:WPP_GLOBAL_Control
0x18001079e  lea     rbx, WPP_GLOBAL_Control
0x1800107a5  mov     rax, [rsp+88h+Src]
0x1800107ad  test    rax, rax
0x1800107b0  jz      loc_1800109FE
0x1800107b6  test    edi, edi
0x1800107b8  jnz     loc_1800109E9
0x1800107be  mov     rcx, [rsp+88h+arg_40]
0x1800107c6  mov     [rcx], rax
0x1800107c9  jmp     loc_1800109F7
0x1800107ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107d5  jmp     loc_180010744
0x1800107da  lea     rbx, [r15+90h]
0x1800107e1  mov     rcx, [rbx]
0x1800107e4  test    rcx, rcx
0x1800107e7  jz      short loc_1800107FC
0x1800107e9  mov     rax, [rcx]
0x1800107ec  mov     rax, [rax+10h]
0x1800107f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107f5  mov     qword ptr [rbx], 0
0x1800107fc  mov     r9, rbx
0x1800107ff  lea     r8, IID_IXWizardTaskEvent
0x180010806  mov     edx, esi
0x180010808  lea     rcx, [r15+8]
0x18001080c  call    ?HrCreateWrappedCOMComponent@@YAJPEBU_GUID@@W4tagXW_WIZARD_TYPE@@0PEAPEAX@Z; HrCreateWrappedCOMComponent(_GUID const *,tagXW_WIZARD_TYPE,_GUID const *,void * *)
0x180010811  mov     edi, eax
0x180010813  test    eax, eax
0x180010815  jns     short loc_180010877
0x180010817  cmp     eax, 80004001h
0x18001081c  jnz     short loc_180010854
0x18001081e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010825  lea     rbx, WPP_GLOBAL_Control
0x18001082c  cmp     rcx, rbx
0x18001082f  jz      short loc_180010885
0x180010831  test    byte ptr [rcx+1Ch], 8
0x180010835  jz      short loc_180010885
0x180010837  mov     edx, 11h
0x18001083c  mov     r9d, 80004001h
0x180010842  mov     rcx, [rcx+10h]
0x180010846  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x18001084d  call    WPP_SF_d
0x180010852  jmp     short loc_18001087E
0x180010854  mov     rcx, cs:WPP_GLOBAL_Control
0x18001085b  lea     rbx, WPP_GLOBAL_Control
0x180010862  cmp     rcx, rbx
0x180010865  jz      short loc_180010885
0x180010867  test    byte ptr [rcx+1Ch], 4
0x18001086b  jz      short loc_180010885
0x18001086d  mov     edx, 12h
0x180010872  mov     r9d, eax
0x180010875  jmp     short loc_180010842
0x180010877  lea     rbx, WPP_GLOBAL_Control
0x18001087e  mov     rcx, cs:WPP_GLOBAL_Control
0x180010885  mov     r10, [r15+90h]
0x18001088c  test    r10, r10
0x18001088f  jz      short loc_1800108E7
0x180010891  mov     rax, [r10]
0x180010894  lea     rcx, [rsp+88h+Src]
0x18001089c  mov     [rsp+88h+var_48], rcx
0x1800108a1  mov     r9d, esi
0x1800108a4  mov     ecx, [rsp+88h+arg_30]
0x1800108ab  mov     r8, r13
0x1800108ae  mov     [rsp+88h+var_50], r12
0x1800108b3  mov     rdx, rbp
0x1800108b6  mov     rax, [rax+38h]
0x1800108ba  mov     [rsp+88h+var_58], ecx
0x1800108be  mov     rcx, [rsp+88h+arg_28]
0x1800108c6  mov     [rsp+88h+var_60], rcx
0x1800108cb  mov     ecx, [rsp+88h+arg_20]
0x1800108d2  mov     [rsp+88h+var_68], ecx
0x1800108d6  mov     rcx, r10
0x1800108d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108e5  mov     edi, eax
0x1800108e7  cmp     edi, 80004001h
0x1800108ed  jnz     loc_180010739
0x1800108f3  sub     esi, 1
0x1800108f6  jz      short loc_180010916
0x1800108f8  sub     esi, 1
0x1800108fb  jz      short loc_180010916
0x1800108fd  sub     esi, 1Eh
0x180010900  jz      short loc_180010916
0x180010902  sub     esi, 1E0h
0x180010908  jz      short loc_180010916
0x18001090a  cmp     esi, 200h
0x180010910  jnz     loc_18001079E
0x180010916  cmp     rcx, rbx
0x180010919  jz      short loc_180010936
0x18001091b  test    byte ptr [rcx+1Ch], 8
0x18001091f  jz      short loc_180010936
0x180010921  mov     rcx, [rcx+10h]
0x180010925  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x18001092c  mov     edx, 13h
0x180010931  call    WPP_SF_
0x180010936  mov     edi, 60h ; '`'
0x18001093b  mov     ecx, edi; cb
0x18001093d  call    cs:__imp_CoTaskMemAlloc
0x180010943  mov     rbx, rax
0x180010946  test    rax, rax
0x180010949  jz      short loc_18001099C
0x18001094b  lea     rcx, [rax+4]; void *
0x18001094f  xor     edx, edx; Val
0x180010951  lea     r8d, [rdi-4]; Size
0x180010955  call    memset_0
0x18001095a  mov     [rbx], edi
0x18001095c  mov     rcx, cs:hModule
0x180010963  or      dword ptr [rbx+4], 88004h
0x18001096a  mov     [rbx+10h], rcx
0x18001096e  xor     edi, edi
0x180010970  mov     qword ptr [rbx+48h], 1B59h
0x180010978  mov     qword ptr [rbx+58h], 1B58h
0x180010980  mov     qword ptr [rbx+18h], 2710h
0x180010988  mov     rcx, cs:WPP_GLOBAL_Control
0x18001098f  mov     [rsp+88h+Src], rbx
0x180010997  jmp     loc_18001073D
0x18001099c  mov     edi, 8007000Eh
0x1800109a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109a8  lea     rbx, WPP_GLOBAL_Control
0x1800109af  cmp     rcx, rbx
0x1800109b2  jz      loc_1800107A5
0x1800109b8  test    byte ptr [rcx+1Ch], 4
0x1800109bc  jz      loc_1800107A5
0x1800109c2  mov     rcx, [rcx+10h]
0x1800109c6  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x1800109cd  mov     edx, 14h
0x1800109d2  mov     r9d, 8007000Eh
0x1800109d8  call    WPP_SF_d
0x1800109dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109e4  jmp     loc_1800107A5
0x1800109e9  mov     rcx, [rsp+88h+Src]; pv
0x1800109f1  call    cs:__imp_CoTaskMemFree
0x1800109f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800109fe  cmp     rcx, rbx
0x180010a01  jz      short loc_180010A21
0x180010a03  test    byte ptr [rcx+1Ch], 10h
0x180010a07  jz      short loc_180010A21
0x180010a09  mov     rcx, [rcx+10h]
0x180010a0d  lea     r8, WPP_2bc823490ca13860ef0fd20ec53590ea_Traceguids
0x180010a14  mov     edx, 16h
0x180010a19  mov     r9d, edi
0x180010a1c  call    WPP_SF_d
0x180010a21  mov     rbx, [rsp+88h+arg_10]
0x180010a29  mov     eax, edi
0x180010a2b  add     rsp, 50h
0x180010a2f  pop     r15
0x180010a31  pop     r14
0x180010a33  pop     r13
0x180010a35  pop     r12
0x180010a37  pop     rdi
0x180010a38  pop     rsi
0x180010a39  pop     rbp
0x180010a3a  retn
```
