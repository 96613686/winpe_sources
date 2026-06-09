# SrSmapiGetSupportedCopyStates(_MI_Context *)

- ea: `0x1800100a8`
- end: `0x18001026c`
- name: `?SrSmapiGetSupportedCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z`
- size: `452`
- prototype: `enum _MI_Result __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800042f0`

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
- `0x1800100a8`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiGetSupportedCopyStates(struct _MI_Context *a1)
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
    v5 = MI_Context_ConstructParameters(a1, &WSP_ReplicationCapabilities_GetSupportedCopyStates_rtti, &instance);
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
0x1800100a8  push    rbp
0x1800100aa  push    rbx
0x1800100ab  push    rsi
0x1800100ac  push    rdi
0x1800100ad  push    r12
0x1800100af  push    r14
0x1800100b1  lea     rbp, [rsp-48h]
0x1800100b6  sub     rsp, 148h
0x1800100bd  mov     rax, cs:__security_cookie
0x1800100c4  xor     rax, rsp
0x1800100c7  mov     [rbp+70h+var_40], rax
0x1800100cb  mov     rsi, rcx
0x1800100ce  mov     rdx, rcx; struct _MI_Context *
0x1800100d1  lea     rcx, [rbp+70h+var_90]; this
0x1800100d5  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x1800100da  nop
0x1800100db  lea     rcx, [rsp+170h+var_138]
0x1800100e0  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x1800100e5  nop
0x1800100e6  mov     [rsp+170h+instance.ft], 0
0x1800100ef  xor     edx, edx; Val
0x1800100f1  lea     r8d, [rdx+70h]; Size
0x1800100f5  lea     rcx, [rsp+170h+instance.classDecl]; void *
0x1800100fa  call    memset_0
0x1800100ff  mov     r12d, 2
0x180010105  mov     [rsp+170h+var_140], r12w
0x18001010b  lea     rdx, [rsp+170h+var_140]
0x180010110  lea     rcx, [rsp+170h+var_138]
0x180010115  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001011a  lea     eax, [r12+2]
0x18001011f  mov     [rsp+170h+var_140], ax
0x180010124  lea     rdx, [rsp+170h+var_140]
0x180010129  lea     rcx, [rsp+170h+var_138]
0x18001012e  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x180010133  lea     eax, [r12+3]
0x180010138  mov     [rsp+170h+var_140], ax
0x18001013d  lea     rdx, [rsp+170h+var_140]
0x180010142  lea     rcx, [rsp+170h+var_138]
0x180010147  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001014c  mov     rcx, qword ptr [rsp+170h+var_138+8]
0x180010151  sub     rcx, qword ptr [rsp+170h+var_138]
0x180010156  sar     rcx, 1
0x180010159  xor     ebx, ebx
0x18001015b  mov     edx, 0FFFFFFFFh
0x180010160  cmp     rcx, rdx
0x180010163  setnbe  bl
0x180010166  mov     r14d, ecx
0x180010169  xor     eax, eax
0x18001016b  cmp     rcx, rdx
0x18001016e  cmova   r14d, eax
0x180010172  ja      loc_1800101FE
0x180010178  lea     r8, [rsp+170h+instance]; instance
0x18001017d  lea     rdx, WSP_ReplicationCapabilities_GetSupportedCopyStates_rtti; methodDecl
0x180010184  mov     rcx, rsi; context
0x180010187  call    MI_Context_ConstructParameters
0x18001018c  mov     edi, eax
0x18001018e  test    eax, eax
0x180010190  jnz     short loc_1800101DB
0x180010192  mov     [rsp+170h+var_114], eax
0x180010196  mov     rcx, qword ptr [rsp+170h+var_138]
0x18001019b  mov     [rsp+170h+var_120], rcx
0x1800101a0  mov     [rsp+170h+var_118], r14d
0x1800101a5  mov     rcx, [rsp+170h+instance.ft]
0x1800101aa  mov     rax, [rcx+50h]
0x1800101ae  mov     [rsp+170h+var_150], edi
0x1800101b2  lea     r9d, [r12+11h]
0x1800101b7  lea     r8, [rsp+170h+var_120]
0x1800101bc  mov     edx, r12d
0x1800101bf  lea     rcx, [rsp+170h+instance]
0x1800101c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101c9  mov     ebx, eax
0x1800101cb  test    eax, eax
0x1800101cd  jnz     short loc_1800101DD
0x1800101cf  mov     eax, [rbp+70h+var_60]
0x1800101d2  mov     [rbp+70h+var_D0], eax
0x1800101d5  mov     [rbp+70h+var_CC], 1
0x1800101d9  jmp     short loc_1800101DD
0x1800101db  mov     ebx, edi
0x1800101dd  test    ebx, ebx
0x1800101df  jnz     short loc_1800101F0
0x1800101e1  lea     rdx, [rsp+170h+instance]
0x1800101e6  mov     rcx, rsi; self
0x1800101e9  call    MI_Instance_Destruct
0x1800101ee  mov     ebx, eax
0x1800101f0  test    edi, edi
0x1800101f2  jnz     short loc_1800101FE
0x1800101f4  lea     rcx, [rsp+170h+instance]; self
0x1800101f9  call    MI_Instance_Destruct
0x1800101fe  mov     edx, ebx; enum _MI_Result
0x180010200  lea     rcx, [rbp+70h+var_90]; this
0x180010204  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x180010209  nop
0x18001020a  mov     rcx, qword ptr [rsp+170h+var_138]
0x18001020f  test    rcx, rcx
0x180010212  jz      short loc_180010239
0x180010214  mov     rdx, [rsp+170h+var_128]
0x180010219  sub     rdx, rcx
0x18001021c  sar     rdx, 1
0x18001021f  add     rdx, rdx
0x180010222  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180010227  xorps   xmm0, xmm0
0x18001022a  movdqu  [rsp+170h+var_138], xmm0
0x180010230  mov     [rsp+170h+var_128], 0
0x180010239  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180010240  mov     [rbp+70h+var_90], rax
0x180010244  lea     rcx, [rbp+70h+var_80]
0x180010248  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001024d  mov     eax, ebx
0x18001024f  mov     rcx, [rbp+70h+var_40]
0x180010253  xor     rcx, rsp; StackCookie
0x180010256  call    __security_check_cookie
0x18001025b  add     rsp, 148h
0x180010262  pop     r14
0x180010264  pop     r12
0x180010266  pop     rdi
0x180010267  pop     rsi
0x180010268  pop     rbx
0x180010269  pop     rbp
0x18001026a  retn
```
