# SrSmapiGetSupportedGroupCopyStates(_MI_Context *)

- ea: `0x1800104f0`
- end: `0x1800106b4`
- name: `?SrSmapiGetSupportedGroupCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z`
- size: `452`
- prototype: `enum _MI_Result __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180004470`

## callees

- `0x1800014e0`
- `0x180001e38`
- `0x18000573c`
- `0x180005930`
- `0x180005948`
- `0x180005cec`
- `0x180006724`
- `0x180008f8c`
- `0x180009028`
- `0x18000df74`
- `0x1800104f0`
- `0x18002d010`

## pseudocode

```c
__int64 __fastcall SrSmapiGetSupportedGroupCopyStates(struct _MI_Context *a1)
{
  unsigned __int64 v2; // rcx
  enum _MI_Result v3; // ebx
  int v4; // r14d
  MI_Result v5; // edi
  __int16 v7; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v8; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h]
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+5Ch] [rbp-A4h]
  MI_Instance instance; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+A0h] [rbp-60h]
  char v15; // [rsp+A4h] [rbp-5Ch]
  _QWORD v16[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v17[32]; // [rsp+F0h] [rbp-10h] BYREF
  int v18; // [rsp+110h] [rbp+10h]

  CWMIContext::CWMIContext((CWMIContext *)v16, a1);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(&v8);
  instance.ft = 0;
  memset_0(&instance.classDecl, 0, 0x70u);
  v7 = 2;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v7 = 4;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v7 = 5;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v2 = (__int64)(*((_QWORD *)&v8 + 1) - v8) >> 1;
  v3 = v2 > 0xFFFFFFFF;
  v4 = v2;
  if ( v2 <= 0xFFFFFFFF )
  {
    v5 = MI_Context_ConstructParameters(a1, &WSP_ReplicationCapabilities_GetSupportedGroupCopyStates_rtti, &instance);
    if ( v5 )
    {
      v3 = v5;
    }
    else
    {
      v12 = 0;
      v10 = v8;
      v11 = v4;
      v3 = ((unsigned int (__fastcall *)(MI_Instance *, __int64, __int64 *, __int64, _DWORD))instance.ft->SetElementAt)(
             &instance,
             2,
             &v10,
             19,
             0);
      if ( v3 == MI_RESULT_OK )
      {
        v14 = v18;
        v15 = 1;
      }
    }
    if ( v3 == MI_RESULT_OK )
      v3 = MI_Instance_Destruct((MI_Instance *)a1);
    if ( v5 == MI_RESULT_OK )
      MI_Instance_Destruct(&instance);
  }
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v16, v3);
  if ( (_QWORD)v8 )
  {
    std::_Deallocate<16>(v8, 2 * ((v9 - (__int64)v8) >> 1));
    v8 = 0;
    v9 = 0;
  }
  v16[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate(v17);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800104f0  push    rbp
0x1800104f2  push    rbx
0x1800104f3  push    rsi
0x1800104f4  push    rdi
0x1800104f5  push    r12
0x1800104f7  push    r14
0x1800104f9  lea     rbp, [rsp-48h]
0x1800104fe  sub     rsp, 148h
0x180010505  mov     rax, cs:__security_cookie
0x18001050c  xor     rax, rsp
0x18001050f  mov     [rbp+70h+var_40], rax
0x180010513  mov     rsi, rcx
0x180010516  mov     rdx, rcx; struct _MI_Context *
0x180010519  lea     rcx, [rbp+70h+var_90]; this
0x18001051d  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x180010522  nop
0x180010523  lea     rcx, [rsp+170h+var_138]
0x180010528  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x18001052d  nop
0x18001052e  mov     [rsp+170h+instance.ft], 0
0x180010537  xor     edx, edx; Val
0x180010539  lea     r8d, [rdx+70h]; Size
0x18001053d  lea     rcx, [rsp+170h+instance.classDecl]; void *
0x180010542  call    memset_0
0x180010547  mov     r12d, 2
0x18001054d  mov     [rsp+170h+var_140], r12w
0x180010553  lea     rdx, [rsp+170h+var_140]
0x180010558  lea     rcx, [rsp+170h+var_138]
0x18001055d  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x180010562  lea     eax, [r12+2]
0x180010567  mov     [rsp+170h+var_140], ax
0x18001056c  lea     rdx, [rsp+170h+var_140]
0x180010571  lea     rcx, [rsp+170h+var_138]
0x180010576  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001057b  lea     eax, [r12+3]
0x180010580  mov     [rsp+170h+var_140], ax
0x180010585  lea     rdx, [rsp+170h+var_140]
0x18001058a  lea     rcx, [rsp+170h+var_138]
0x18001058f  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x180010594  mov     rcx, qword ptr [rsp+170h+var_138+8]
0x180010599  sub     rcx, qword ptr [rsp+170h+var_138]
0x18001059e  sar     rcx, 1
0x1800105a1  xor     ebx, ebx
0x1800105a3  mov     edx, 0FFFFFFFFh
0x1800105a8  cmp     rcx, rdx
0x1800105ab  setnbe  bl
0x1800105ae  mov     r14d, ecx
0x1800105b1  xor     eax, eax
0x1800105b3  cmp     rcx, rdx
0x1800105b6  cmova   r14d, eax
0x1800105ba  ja      loc_180010646
0x1800105c0  lea     r8, [rsp+170h+instance]; instance
0x1800105c5  lea     rdx, WSP_ReplicationCapabilities_GetSupportedGroupCopyStates_rtti; methodDecl
0x1800105cc  mov     rcx, rsi; context
0x1800105cf  call    MI_Context_ConstructParameters
0x1800105d4  mov     edi, eax
0x1800105d6  test    eax, eax
0x1800105d8  jnz     short loc_180010623
0x1800105da  mov     [rsp+170h+var_114], eax
0x1800105de  mov     rcx, qword ptr [rsp+170h+var_138]
0x1800105e3  mov     [rsp+170h+var_120], rcx
0x1800105e8  mov     [rsp+170h+var_118], r14d
0x1800105ed  mov     rcx, [rsp+170h+instance.ft]
0x1800105f2  mov     rax, [rcx+50h]
0x1800105f6  mov     [rsp+170h+var_150], edi
0x1800105fa  lea     r9d, [r12+11h]
0x1800105ff  lea     r8, [rsp+170h+var_120]
0x180010604  mov     edx, r12d
0x180010607  lea     rcx, [rsp+170h+instance]
0x18001060c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010611  mov     ebx, eax
0x180010613  test    eax, eax
0x180010615  jnz     short loc_180010625
0x180010617  mov     eax, [rbp+70h+var_60]
0x18001061a  mov     [rbp+70h+var_D0], eax
0x18001061d  mov     [rbp+70h+var_CC], 1
0x180010621  jmp     short loc_180010625
0x180010623  mov     ebx, edi
0x180010625  test    ebx, ebx
0x180010627  jnz     short loc_180010638
0x180010629  lea     rdx, [rsp+170h+instance]
0x18001062e  mov     rcx, rsi; self
0x180010631  call    MI_Instance_Destruct
0x180010636  mov     ebx, eax
0x180010638  test    edi, edi
0x18001063a  jnz     short loc_180010646
0x18001063c  lea     rcx, [rsp+170h+instance]; self
0x180010641  call    MI_Instance_Destruct
0x180010646  mov     edx, ebx; enum _MI_Result
0x180010648  lea     rcx, [rbp+70h+var_90]; this
0x18001064c  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x180010651  nop
0x180010652  mov     rcx, qword ptr [rsp+170h+var_138]
0x180010657  test    rcx, rcx
0x18001065a  jz      short loc_180010681
0x18001065c  mov     rdx, [rsp+170h+var_128]
0x180010661  sub     rdx, rcx
0x180010664  sar     rdx, 1
0x180010667  add     rdx, rdx
0x18001066a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001066f  xorps   xmm0, xmm0
0x180010672  movdqu  [rsp+170h+var_138], xmm0
0x180010678  mov     [rsp+170h+var_128], 0
0x180010681  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180010688  mov     [rbp+70h+var_90], rax
0x18001068c  lea     rcx, [rbp+70h+var_80]
0x180010690  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010695  mov     eax, ebx
0x180010697  mov     rcx, [rbp+70h+var_40]
0x18001069b  xor     rcx, rsp; StackCookie
0x18001069e  call    __security_check_cookie
0x1800106a3  add     rsp, 148h
0x1800106aa  pop     r14
0x1800106ac  pop     r12
0x1800106ae  pop     rdi
0x1800106af  pop     rsi
0x1800106b0  pop     rbx
0x1800106b1  pop     rbp
0x1800106b2  retn
```
