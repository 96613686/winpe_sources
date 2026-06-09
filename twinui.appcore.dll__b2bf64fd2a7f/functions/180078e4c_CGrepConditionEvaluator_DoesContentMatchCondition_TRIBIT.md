# CGrepConditionEvaluator::DoesContentMatchCondition(TRIBIT *)

- ea: `0x180078e4c`
- end: `0x18007910c`
- name: `?DoesContentMatchCondition@CGrepConditionEvaluator@@QEAAJPEAW4TRIBIT@@@Z`
- size: `704`
- prototype: `__int64 __fastcall(CGrepConditionEvaluator *__hidden this, enum TRIBIT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007a4d4`

## callees

- `0x18002b1b0`
- `0x18002bc68`
- `0x18002ce82`
- `0x18006e564`
- `0x180077f04`
- `0x180078e4c`
- `0x1800791dc`
- `0x18007a67c`
- `0x18007e198`
- `0x180080018`
- `0x1800811c0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180079078`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180079078`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079085`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079085`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180078ed1`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180078ed1`

## pseudocode

```c
__int64 __fastcall CGrepConditionEvaluator::DoesContentMatchCondition(
        CGrepConditionEvaluator *this,
        enum TRIBIT *a2,
        __int64 a3)
{
  HRESULT inited; // ebx
  __int64 v6; // r8
  __int64 *v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  void (__fastcall *v10)(__int64 *); // rax
  __int64 v11; // rcx
  HRESULT v12; // eax
  int i; // esi
  struct _DPA *v14; // rcx
  int v15; // eax
  struct ICondition *Ptr; // rax
  struct ICondition *v17; // r14
  void *v18; // rcx
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v21[3]; // [rsp+34h] [rbp-CCh] BYREF
  _QWORD v22[17]; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+C8h] [rbp-38h]
  __int64 v24; // [rsp+D0h] [rbp-30h]
  __int64 v25; // [rsp+D8h] [rbp-28h]
  __int64 v26; // [rsp+E0h] [rbp-20h]
  __int64 v27; // [rsp+E8h] [rbp-18h]
  __int64 v28; // [rsp+F0h] [rbp-10h]
  void *ppv[2]; // [rsp+150h] [rbp+50h] BYREF

  if ( (byte_1800B3382 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start,
      a3,
      1,
      ppv);
  *(_DWORD *)a2 = 0;
  inited = CGrepConditionEvaluator::_InitFilter(this);
  if ( !inited )
  {
    ppv[0] = 0;
    inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, ppv);
    if ( inited >= 0 )
    {
      IUnknown_Set_0((IUnknown **)this + 1, (IUnknown *)ppv[0]);
      v7 = (__int64 *)*((_QWORD *)this + 13);
      v8 = *((_QWORD *)this + 23);
      v20 = 0;
      v22[0] = v7;
      v9 = *v7;
      v22[1] = v8;
      v22[8] = 0;
      v23 = 1;
      v10 = *(void (__fastcall **)(__int64 *))(v9 + 8);
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v10(v7);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
LABEL_34:
      if ( !inited )
      {
        while ( v20 != 1 )
        {
          v11 = *((_QWORD *)this + 23);
          if ( v11 )
            inited = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11);
          if ( inited )
            break;
          while ( 1 )
          {
            memset_0((char *)this + 112, 0, 0x40u);
            v12 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 13) + 32LL))(
                    *((_QWORD *)this + 13),
                    (char *)this + 112);
            inited = v12;
            if ( v12 )
              break;
            if ( (*((_DWORD *)this + 30) & 3) != 0 )
            {
              ++*((_DWORD *)this + 44);
              goto LABEL_18;
            }
          }
          if ( (unsigned int)(v12 + 2147215609) <= 1 || v12 == -2147215616 || v12 == 268036 )
            inited = 1;
LABEL_18:
          if ( inited )
            break;
          if ( (*((_BYTE *)this + 120) & 1) != 0 )
          {
            inited = CGrep::GrepText(
                       (CGrep *)v22,
                       (const struct tagSTAT_CHUNK *)((char *)this + 112),
                       this,
                       (enum TRIBIT *)&v20);
            goto LABEL_34;
          }
          if ( (*((_BYTE *)this + 120) & 2) != 0 )
          {
            for ( i = 0; ; ++i )
            {
              v14 = (struct _DPA *)*((_QWORD *)this + 10);
              v15 = v14 ? *(_DWORD *)v14 : 0;
              if ( i >= v15 || inited < 0 || v20 == 1 )
                break;
              Ptr = (struct ICondition *)g_pfn_DPA_GetPtr(v14, i);
              v21[0] = 0;
              v17 = Ptr;
              inited = GetEvalStateEx(Ptr, L"ES", v21);
              if ( inited >= 0 && !v21[0] )
                inited = CGrepConditionEvaluator::EvalValueChunk(this, v17, (enum TRIBIT *)&v20);
            }
            PropVariantClear(*((PROPVARIANT **)this + 25));
            CoTaskMemFree(*((LPVOID *)this + 25));
            *((_QWORD *)this + 25) = 0;
            goto LABEL_34;
          }
        }
      }
      v18 = ppv[0];
      *(_DWORD *)a2 = v20;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
      CGrep::~CGrep((CGrep *)v22);
    }
  }
  if ( (byte_1800B3382 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop,
      v6,
      1,
      ppv);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180078e4c  mov     [rsp-8+arg_10], rbx
0x180078e51  push    rbp
0x180078e52  push    rsi
0x180078e53  push    rdi
0x180078e54  push    r12
0x180078e56  push    r13
0x180078e58  push    r14
0x180078e5a  push    r15
0x180078e5c  lea     rbp, [rsp-70h]
0x180078e61  sub     rsp, 170h
0x180078e68  mov     rax, cs:__security_cookie
0x180078e6f  xor     rax, rsp
0x180078e72  mov     [rbp+0A0h+var_40], rax
0x180078e76  test    cs:byte_1800B3382, 20h
0x180078e7d  mov     r15, rdx
0x180078e80  mov     rdi, rcx
0x180078e83  mov     r13d, 1
0x180078e89  jz      short loc_180078EAA
0x180078e8b  lea     rax, [rbp+0A0h+ppv]
0x180078e8f  mov     r9d, r13d
0x180078e92  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Start
0x180078e99  mov     [rsp+1A0h+var_180], rax
0x180078e9e  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180078ea5  call    McGenEventWrite_EventWriteTransfer
0x180078eaa  xor     r12d, r12d
0x180078ead  mov     rcx, rdi; this
0x180078eb0  mov     [r15], r12d
0x180078eb3  call    ?_InitFilter@CGrepConditionEvaluator@@AEAAJXZ; CGrepConditionEvaluator::_InitFilter(void)
0x180078eb8  mov     ebx, eax
0x180078eba  test    eax, eax
0x180078ebc  jnz     loc_1800790BB
0x180078ec2  lea     rdx, [rbp+0A0h+ppv]; ppv
0x180078ec6  mov     [rbp+0A0h+ppv], r12
0x180078eca  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x180078ed1  call    cs:__imp_PSCreateMemoryPropertyStore
0x180078ed7  mov     ebx, eax
0x180078ed9  test    eax, eax
0x180078edb  js      loc_1800790BB
0x180078ee1  mov     rdx, [rbp+0A0h+ppv]; punk
0x180078ee5  lea     rcx, [rdi+8]; ppunk
0x180078ee9  call    IUnknown_Set_0
0x180078eee  mov     rcx, [rdi+68h]
0x180078ef2  mov     rsi, [rdi+0B8h]
0x180078ef9  mov     [rsp+1A0h+var_170], r12d
0x180078efe  mov     [rsp+1A0h+var_160], rcx
0x180078f03  mov     rax, [rcx]
0x180078f06  mov     [rsp+1A0h+var_158], rsi
0x180078f0b  mov     [rbp+0A0h+var_120], r12
0x180078f0f  mov     [rbp+0A0h+var_D8], r13d
0x180078f13  mov     rax, [rax+8]
0x180078f17  mov     [rbp+0A0h+var_D0], r12
0x180078f1b  mov     [rbp+0A0h+var_C8], r12
0x180078f1f  mov     [rbp+0A0h+var_C0], r12
0x180078f23  mov     [rbp+0A0h+var_B8], r12
0x180078f27  mov     [rbp+0A0h+var_B0], r12
0x180078f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f30  test    rsi, rsi
0x180078f33  jz      loc_180079092
0x180078f39  mov     rax, [rsi]
0x180078f3c  mov     rcx, rsi
0x180078f3f  mov     rax, [rax+8]
0x180078f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f48  jmp     loc_180079092
0x180078f4d  cmp     [rsp+1A0h+var_170], r13d
0x180078f52  jz      loc_18007909A
0x180078f58  mov     rcx, [rdi+0B8h]
0x180078f5f  test    rcx, rcx
0x180078f62  jz      short loc_180078F72
0x180078f64  mov     rax, [rcx]
0x180078f67  mov     rax, [rax+18h]
0x180078f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f70  mov     ebx, eax
0x180078f72  test    ebx, ebx
0x180078f74  jnz     loc_18007909A
0x180078f7a  lea     rsi, [rdi+70h]
0x180078f7e  xor     edx, edx; Val
0x180078f80  mov     rcx, rsi; void *
0x180078f83  lea     r8d, [rdx+40h]; Size
0x180078f87  call    memset_0
0x180078f8c  mov     rcx, [rdi+68h]
0x180078f90  mov     rdx, rsi
0x180078f93  mov     rax, [rcx]
0x180078f96  mov     rax, [rax+20h]
0x180078f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078f9f  mov     ebx, eax
0x180078fa1  test    eax, eax
0x180078fa3  jnz     short loc_180078FB5
0x180078fa5  mov     eax, [rdi+78h]
0x180078fa8  test    al, 3
0x180078faa  jz      short loc_180078F7E
0x180078fac  add     [rdi+0B0h], r13d
0x180078fb3  jmp     short loc_180078FD2
0x180078fb5  add     eax, 7FFBE8F9h
0x180078fba  cmp     eax, r13d
0x180078fbd  jbe     short loc_180078FCF
0x180078fbf  cmp     ebx, 80041700h
0x180078fc5  jz      short loc_180078FCF
0x180078fc7  cmp     ebx, 41704h
0x180078fcd  jnz     short loc_180078FD2
0x180078fcf  mov     ebx, r13d
0x180078fd2  test    ebx, ebx
0x180078fd4  jnz     loc_18007909A
0x180078fda  test    [rdi+78h], r13b
0x180078fde  jz      short loc_180078FFC
0x180078fe0  lea     r9, [rsp+1A0h+var_170]; enum TRIBIT *
0x180078fe5  mov     r8, rdi; struct CConditionEvaluator *
0x180078fe8  mov     rdx, rsi; struct tagSTAT_CHUNK *
0x180078feb  lea     rcx, [rsp+1A0h+var_160]; this
0x180078ff0  call    ?GrepText@CGrep@@QEAAJAEBUtagSTAT_CHUNK@@PEAVCConditionEvaluator@@PEAW4TRIBIT@@@Z; CGrep::GrepText(tagSTAT_CHUNK const &,CConditionEvaluator *,TRIBIT *)
0x180078ff5  mov     ebx, eax
0x180078ff7  jmp     loc_180079092
0x180078ffc  test    byte ptr [rsi+8], 2
0x180079000  jz      loc_180078F4D
0x180079006  mov     esi, r12d
0x180079009  mov     rcx, [rdi+50h]; hdpa
0x18007900d  test    rcx, rcx
0x180079010  jz      short loc_180079016
0x180079012  mov     eax, [rcx]
0x180079014  jmp     short loc_180079019
0x180079016  mov     eax, r12d
0x180079019  cmp     esi, eax
0x18007901b  jge     short loc_180079071
0x18007901d  test    ebx, ebx
0x18007901f  js      short loc_180079071
0x180079021  cmp     [rsp+1A0h+var_170], r13d
0x180079026  jz      short loc_180079071
0x180079028  movsxd  rdx, esi; i
0x18007902b  call    cs:g_pfn_DPA_GetPtr
0x180079031  lea     r8, [rsp+1A0h+var_16C]
0x180079036  mov     [rsp+1A0h+var_16C], r12d
0x18007903b  mov     rcx, rax
0x18007903e  lea     rdx, aEs; "ES"
0x180079045  mov     r14, rax
0x180079048  call    GetEvalStateEx
0x18007904d  mov     ebx, eax
0x18007904f  test    eax, eax
0x180079051  js      short loc_18007906C
0x180079053  cmp     [rsp+1A0h+var_16C], r12d
0x180079058  jnz     short loc_18007906C
0x18007905a  lea     r8, [rsp+1A0h+var_170]; enum TRIBIT *
0x18007905f  mov     rdx, r14; struct ICondition *
0x180079062  mov     rcx, rdi; this
0x180079065  call    ?EvalValueChunk@CGrepConditionEvaluator@@AEAAJPEAUICondition@@PEAW4TRIBIT@@@Z; CGrepConditionEvaluator::EvalValueChunk(ICondition *,TRIBIT *)
0x18007906a  mov     ebx, eax
0x18007906c  add     esi, r13d
0x18007906f  jmp     short loc_180079009
0x180079071  mov     rcx, [rdi+0C8h]; pvar
0x180079078  call    cs:__imp_PropVariantClear
0x18007907e  mov     rcx, [rdi+0C8h]; pv
0x180079085  call    cs:__imp_CoTaskMemFree
0x18007908b  mov     [rdi+0C8h], r12
0x180079092  test    ebx, ebx
0x180079094  jz      loc_180078F4D
0x18007909a  mov     eax, [rsp+1A0h+var_170]
0x18007909e  mov     rcx, [rbp+0A0h+ppv]
0x1800790a2  mov     [r15], eax
0x1800790a5  mov     rax, [rcx]
0x1800790a8  mov     rax, [rax+10h]
0x1800790ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800790b1  lea     rcx, [rsp+1A0h+var_160]; this
0x1800790b6  call    ??1CGrep@@QEAA@XZ; CGrep::~CGrep(void)
0x1800790bb  test    cs:byte_1800B3382, 20h
0x1800790c2  jz      short loc_1800790E3
0x1800790c4  lea     rax, [rbp+0A0h+ppv]
0x1800790c8  mov     r9d, r13d
0x1800790cb  lea     rdx, ShellTraceId_Shell32_CGrepConditionEvaluator_DoesContentMatchCondition_Stop
0x1800790d2  mov     [rsp+1A0h+var_180], rax
0x1800790d7  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x1800790de  call    McGenEventWrite_EventWriteTransfer
0x1800790e3  mov     eax, ebx
0x1800790e5  mov     rcx, [rbp+0A0h+var_40]
0x1800790e9  xor     rcx, rsp; StackCookie
0x1800790ec  call    __security_check_cookie
0x1800790f1  mov     rbx, [rsp+1A0h+arg_10]
0x1800790f9  add     rsp, 170h
0x180079100  pop     r15
0x180079102  pop     r14
0x180079104  pop     r13
0x180079106  pop     r12
0x180079108  pop     rdi
0x180079109  pop     rsi
0x18007910a  pop     rbp
0x18007910b  retn
```
