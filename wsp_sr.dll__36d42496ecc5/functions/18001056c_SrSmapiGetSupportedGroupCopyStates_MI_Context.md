# SrSmapiGetSupportedGroupCopyStates(_MI_Context *)

- ea: `0x18001056c`
- end: `0x18001074f`
- name: `?SrSmapiGetSupportedGroupCopyStates@@YA?AW4_MI_Result@@PEAU_MI_Context@@@Z`
- size: `483`
- prototype: `__int64 __fastcall(struct _MI_Context *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800044d0`

## callees

- `0x1800014e0`
- `0x180001e08`
- `0x18000570c`
- `0x1800058f8`
- `0x180005910`
- `0x180005cac`
- `0x1800066d8`
- `0x180008df8`
- `0x18000e02c`
- `0x18001056c`
- `0x18002d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SrSmapiGetSupportedGroupCopyStates(struct _MI_Context *a1)
{
  MI_Uint32 v2; // ebx
  int v3; // r14d
  int v4; // eax
  int v5; // esi
  __int16 v7; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v8; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v9; // [rsp+48h] [rbp-B8h]
  __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+58h] [rbp-A8h]
  int v12; // [rsp+5Ch] [rbp-A4h]
  MI_Instance self; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+A0h] [rbp-60h]
  char v15; // [rsp+A4h] [rbp-5Ch]
  _QWORD v16[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v17[32]; // [rsp+F0h] [rbp-10h] BYREF
  int v18; // [rsp+110h] [rbp+10h]

  CWMIContext::CWMIContext((CWMIContext *)v16, a1);
  std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(&v8);
  self.ft = 0;
  memset_0(&self.classDecl, 0, 0x70u);
  v7 = 2;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v2 = 4;
  v7 = 4;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v7 = 5;
  std::vector<unsigned short>::push_back(&v8, &v7);
  v3 = (__int64)(*((_QWORD *)&v8 + 1) - v8) >> 1;
  if ( (unsigned __int64)((__int64)(*((_QWORD *)&v8 + 1) - v8) >> 1) > 0xFFFFFFFF )
  {
    v2 = 1;
    goto LABEL_13;
  }
  if ( a1 && a1->ft )
  {
    v4 = ((__int64 (__fastcall *)(struct _MI_Context *, __int64 *, MI_Instance *))a1->ft->ConstructParameters)(
           a1,
           &WSP_ReplicationCapabilities_GetSupportedGroupCopyStates_rtti,
           &self);
    v5 = v4;
    if ( !v4 )
    {
      v12 = 0;
      v10 = v8;
      v11 = v3;
      v4 = ((__int64 (__fastcall *)(MI_Instance *, __int64, __int64 *, __int64, _DWORD))self.ft->SetElementAt)(
             &self,
             2,
             &v10,
             19,
             0);
      if ( !v4 )
      {
        v14 = v18;
        v15 = 1;
        if ( !a1->ft )
          goto LABEL_11;
        v4 = ((__int64 (__fastcall *)(struct _MI_Context *, MI_Instance *))a1->ft->PostInstance)(a1, &self);
      }
    }
  }
  else
  {
    v5 = 4;
    v4 = 4;
  }
  v2 = v4;
LABEL_11:
  if ( !v5 )
    MI_Instance_Destruct(&self);
LABEL_13:
  CWMIContext::EvaluateErrorsAndPostResult((CWMIContext *)v16, v2);
  if ( (_QWORD)v8 )
  {
    std::_Deallocate<16>((void *)v8, 2 * ((v9 - (__int64)v8) >> 1));
    v8 = 0;
    v9 = 0;
  }
  v16[0] = &CWMIContext::`vftable';
  std::wstring::_Tidy_deallocate((__int64)v17);
  return v2;
}

```

## disassembly

```asm
0x18001056c  push    rbp
0x18001056e  push    rbx
0x18001056f  push    rsi
0x180010570  push    rdi
0x180010571  push    r12
0x180010573  push    r14
0x180010575  lea     rbp, [rsp-48h]
0x18001057a  sub     rsp, 148h
0x180010581  mov     rax, cs:__security_cookie
0x180010588  xor     rax, rsp
0x18001058b  mov     [rbp+70h+var_40], rax
0x18001058f  mov     rdi, rcx
0x180010592  mov     rdx, rcx; struct _MI_Context *
0x180010595  lea     rcx, [rbp+70h+var_90]; this
0x180010599  call    ??0CWMIContext@@QEAA@PEAU_MI_Context@@@Z; CWMIContext::CWMIContext(_MI_Context *)
0x18001059e  nop
0x18001059f  lea     rcx, [rsp+170h+var_138]
0x1800105a4  call    ??0?$vector@VMSFT_StorageNode@srstor@@V?$allocator@VMSFT_StorageNode@srstor@@@std@@@std@@QEAA@XZ; std::vector<srstor::MSFT_StorageNode>::vector<srstor::MSFT_StorageNode>(void)
0x1800105a9  nop
0x1800105aa  mov     [rsp+170h+self.ft], 0
0x1800105b3  xor     edx, edx; Val
0x1800105b5  lea     r8d, [rdx+70h]; Size
0x1800105b9  lea     rcx, [rsp+170h+self.classDecl]; void *
0x1800105be  call    memset_0
0x1800105c3  mov     r12d, 2
0x1800105c9  mov     [rsp+170h+var_140], r12w
0x1800105cf  lea     rdx, [rsp+170h+var_140]
0x1800105d4  lea     rcx, [rsp+170h+var_138]
0x1800105d9  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1800105de  lea     ebx, [r12+2]
0x1800105e3  mov     [rsp+170h+var_140], bx
0x1800105e8  lea     rdx, [rsp+170h+var_140]
0x1800105ed  lea     rcx, [rsp+170h+var_138]
0x1800105f2  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1800105f7  lea     eax, [rbx+1]
0x1800105fa  mov     [rsp+170h+var_140], ax
0x1800105ff  lea     rdx, [rsp+170h+var_140]
0x180010604  lea     rcx, [rsp+170h+var_138]
0x180010609  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x18001060e  mov     rcx, qword ptr [rsp+170h+var_138+8]
0x180010613  sub     rcx, qword ptr [rsp+170h+var_138]
0x180010618  sar     rcx, 1
0x18001061b  xor     edx, edx
0x18001061d  mov     r8d, 0FFFFFFFFh
0x180010623  cmp     rcx, r8
0x180010626  setnbe  dl
0x180010629  mov     r14d, ecx
0x18001062c  xor     eax, eax
0x18001062e  cmp     rcx, r8
0x180010631  cmova   r14d, eax
0x180010635  ja      loc_1800106E0
0x18001063b  test    rdi, rdi
0x18001063e  jz      loc_1800106CA
0x180010644  mov     rax, [rdi]
0x180010647  test    rax, rax
0x18001064a  jz      short loc_1800106CA
0x18001064c  lea     r8, [rsp+170h+self]
0x180010651  lea     rdx, WSP_ReplicationCapabilities_GetSupportedGroupCopyStates_rtti
0x180010658  mov     rcx, rdi
0x18001065b  mov     rax, [rax+20h]
0x18001065f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010664  mov     esi, eax
0x180010666  test    eax, eax
0x180010668  jnz     short loc_1800106CE
0x18001066a  mov     [rsp+170h+var_114], eax
0x18001066e  mov     rcx, qword ptr [rsp+170h+var_138]
0x180010673  mov     [rsp+170h+var_120], rcx
0x180010678  mov     [rsp+170h+var_118], r14d
0x18001067d  mov     rcx, [rsp+170h+self.ft]
0x180010682  mov     rax, [rcx+50h]
0x180010686  mov     [rsp+170h+var_150], esi
0x18001068a  lea     r9d, [r12+11h]
0x18001068f  lea     r8, [rsp+170h+var_120]
0x180010694  mov     edx, r12d
0x180010697  lea     rcx, [rsp+170h+self]
0x18001069c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106a1  test    eax, eax
0x1800106a3  jnz     short loc_1800106CE
0x1800106a5  mov     ecx, [rbp+70h+var_60]
0x1800106a8  mov     [rbp+70h+var_D0], ecx
0x1800106ab  mov     [rbp+70h+var_CC], 1
0x1800106af  mov     rax, [rdi]
0x1800106b2  test    rax, rax
0x1800106b5  jz      short loc_1800106D0
0x1800106b7  lea     rdx, [rsp+170h+self]
0x1800106bc  mov     rcx, rdi
0x1800106bf  mov     rax, [rax+8]
0x1800106c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106c8  jmp     short loc_1800106CE
0x1800106ca  mov     esi, ebx
0x1800106cc  mov     eax, ebx
0x1800106ce  mov     ebx, eax
0x1800106d0  test    esi, esi
0x1800106d2  jnz     short loc_1800106E2
0x1800106d4  lea     rcx, [rsp+170h+self]; self
0x1800106d9  call    MI_Instance_Destruct
0x1800106de  jmp     short loc_1800106E2
0x1800106e0  mov     ebx, edx
0x1800106e2  mov     edx, ebx; enum _MI_Result
0x1800106e4  lea     rcx, [rbp+70h+var_90]; this
0x1800106e8  call    ?EvaluateErrorsAndPostResult@CWMIContext@@QEAAXW4_MI_Result@@@Z; CWMIContext::EvaluateErrorsAndPostResult(_MI_Result)
0x1800106ed  nop
0x1800106ee  mov     rcx, qword ptr [rsp+170h+var_138]
0x1800106f3  test    rcx, rcx
0x1800106f6  jz      short loc_18001071D
0x1800106f8  mov     rdx, [rsp+170h+var_128]
0x1800106fd  sub     rdx, rcx
0x180010700  sar     rdx, 1
0x180010703  add     rdx, rdx
0x180010706  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001070b  xorps   xmm0, xmm0
0x18001070e  movdqu  [rsp+170h+var_138], xmm0
0x180010714  mov     [rsp+170h+var_128], 0
0x18001071d  lea     rax, ??_7CWMIContext@@6B@; const CWMIContext::`vftable'
0x180010724  mov     [rbp+70h+var_90], rax
0x180010728  lea     rcx, [rbp+70h+var_80]
0x18001072c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010731  mov     eax, ebx
0x180010733  mov     rcx, [rbp+70h+var_40]
0x180010737  xor     rcx, rsp; StackCookie
0x18001073a  call    __security_check_cookie
0x18001073f  add     rsp, 148h
0x180010746  pop     r14
0x180010748  pop     r12
0x18001074a  pop     rdi
0x18001074b  pop     rsi
0x18001074c  pop     rbx
0x18001074d  pop     rbp
0x18001074e  retn
```
