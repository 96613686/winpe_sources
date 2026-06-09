# __InternalCxxFrameHandler<__FrameHandler4>(EHExceptionRecord *,unsigned __int64 *,_CONTEXT *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int,unsigned __int64 *,uchar)

- ea: `0x1400040e0`
- end: `0x140004384`
- name: `??$__InternalCxxFrameHandler@V__FrameHandler4@@@@YA?AW4_EXCEPTION_DISPOSITION@@PEAUEHExceptionRecord@@PEA_KPEAU_CONTEXT@@PEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@H1E@Z`
- size: `676`
- prototype: `__int64 __usercall@<rax>(struct EHExceptionRecord *@<rcx>, unsigned __int64 *@<rdx>, struct FH4::FuncInfo4 *, int, __int64, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000438c`

## callees

- `0x1400024e4`
- `0x140002a98`
- `0x140003008`
- `0x140003188`
- `0x140003624`
- `0x1400040e0`
- `0x140004468`
- `0x140004b20`
- `0x140005278`
- `0x1400056be`
- `0x1400059e0`

## pseudocode

```c
__int64 __fastcall __InternalCxxFrameHandler<__FrameHandler4>(
        struct EHExceptionRecord *a1,
        unsigned __int64 *a2,
        __int64 a3,
        struct _xDISPATCHER_CONTEXT *a4,
        struct FH4::FuncInfo4 *a5,
        int a6,
        __int64 a7,
        unsigned __int8 a8)
{
  int v12; // ebp
  _BYTE *v13; // rdx
  int pThrowImageBase; // r9d
  _BYTE *v15; // r8
  unsigned __int64 *pExceptionObject; // rcx
  _BYTE *v17; // rdx
  __int64 pForwardCompat; // r14
  __int64 ThrowImageBase; // rax
  _DWORD v21[12]; // [rsp+50h] [rbp-48h] BYREF

  _except_validate_context_record(a3);
  v12 = 0;
  if ( !*(_DWORD *)(_vcrt_getptd() + 64) && a1->ExceptionCode != -529697949 )
  {
    if ( a1->ExceptionCode != -2147483607 )
      goto LABEL_6;
    if ( a1->NumberParameters != 15 )
      goto LABEL_7;
    if ( *(_QWORD *)&a1[1].params.magicNumber != 429065504 )
    {
LABEL_6:
      if ( a1->ExceptionCode != -2147483610 )
      {
LABEL_7:
        if ( (*(_BYTE *)a5 & 0x20) != 0 )
          return 1;
      }
    }
  }
  if ( (a1->ExceptionFlags & 0x66) != 0 )
  {
    if ( !*((_DWORD *)a5 + 2) )
      return 1;
    v13 = (_BYTE *)(*((int *)a5 + 2) + a4->ImageBase);
    if ( !(*(_DWORD *)&v13[-*((char *)&FH4::s_negLengthTab + (*v13 & 0xF)) - 4] >> *((_BYTE *)&FH4::s_shiftTab
                                                                                   + (*v13 & 0xF)))
      || a6 )
    {
      return 1;
    }
    if ( (a1->ExceptionFlags & 0x20) != 0 )
    {
      if ( a1->ExceptionCode == -2147483610 )
      {
        pThrowImageBase = __FrameHandler4::StateFromIp(a5, a4, a4->TargetIp);
        if ( pThrowImageBase >= -1 )
        {
          if ( *((_DWORD *)a5 + 2) )
          {
            v15 = (_BYTE *)(*((int *)a5 + 2) + a4->ImageBase);
            v12 = *(_DWORD *)&v15[-*((char *)&FH4::s_negLengthTab + (*v15 & 0xF)) - 4] >> *((_BYTE *)&FH4::s_shiftTab
                                                                                          + (*v15 & 0xF));
          }
          if ( pThrowImageBase < v12 )
          {
            pExceptionObject = a2;
LABEL_19:
            __FrameHandler4::FrameUnwindToState(pExceptionObject, a4, a5, pThrowImageBase);
            return 1;
          }
        }
        goto LABEL_35;
      }
      if ( a1->ExceptionCode == -2147483607 )
      {
        pThrowImageBase = (int)a1->params.pThrowImageBase;
        if ( pThrowImageBase >= -1 )
        {
          v17 = (_BYTE *)(*((int *)a5 + 2) + a4->ImageBase);
          if ( pThrowImageBase < *(_DWORD *)&v17[-*((char *)&FH4::s_negLengthTab + (*v17 & 0xF)) - 4] >> *((_BYTE *)&FH4::s_shiftTab + (*v17 & 0xF)) )
          {
            pExceptionObject = (unsigned __int64 *)a1->params.pExceptionObject;
            goto LABEL_19;
          }
        }
LABEL_35:
        abort();
      }
    }
    __FrameHandler4::FrameUnwindToEmptyState(a2, a4, a5);
    return 1;
  }
  FH4::TryBlockMap4::TryBlockMap4((FH4::TryBlockMap4 *)v21, a5, a4->ImageBase);
  if ( v21[0] || (*(_BYTE *)a5 & 0x40) != 0 )
  {
    if ( a1->ExceptionCode == -529697949 && a1->NumberParameters >= 3 && a1->params.magicNumber > 0x19930522 )
    {
      pForwardCompat = a1->params.pThrowInfo->pForwardCompat;
      if ( (_DWORD)pForwardCompat )
      {
        ThrowImageBase = GetThrowImageBase();
        if ( pForwardCompat + ThrowImageBase )
          return ((__int64 (__fastcall *)(struct EHExceptionRecord *, unsigned __int64 *, __int64, struct _xDISPATCHER_CONTEXT *, struct FH4::FuncInfo4 *, int, __int64, _DWORD))(pForwardCompat + ThrowImageBase))(
                   a1,
                   a2,
                   a3,
                   a4,
                   a5,
                   a6,
                   a7,
                   a8);
      }
    }
    FindHandler___FrameHandler4_(a1, a2, a3, (__int64)a4, a5, a8, a6, a7);
  }
  return 1;
}

```

## disassembly

```asm
0x1400040e0  mov     rax, rsp
0x1400040e3  mov     [rax+8], rbx
0x1400040e7  mov     [rax+10h], rbp
0x1400040eb  mov     [rax+18h], rsi
0x1400040ef  mov     [rax+20h], rdi
0x1400040f3  push    r12
0x1400040f5  push    r14
0x1400040f7  push    r15
0x1400040f9  sub     rsp, 80h
0x140004100  mov     rbx, rcx
0x140004103  mov     rsi, r9
0x140004106  mov     rcx, r8
0x140004109  mov     r12, r8
0x14000410c  mov     r15, rdx
0x14000410f  call    __except_validate_context_record
0x140004114  call    __vcrt_getptd
0x140004119  mov     rdi, [rsp+98h+arg_20]
0x140004121  xor     ebp, ebp
0x140004123  mov     r14d, 0E06D7363h
0x140004129  mov     r8d, 80000029h
0x14000412f  mov     r9d, 80000026h
0x140004135  cmp     [rax+40h], ebp
0x140004138  jnz     short loc_140004162
0x14000413a  cmp     [rbx], r14d
0x14000413d  jz      short loc_140004162
0x14000413f  cmp     [rbx], r8d
0x140004142  jnz     short loc_140004154
0x140004144  cmp     dword ptr [rbx+18h], 0Fh
0x140004148  jnz     short loc_140004159
0x14000414a  cmp     qword ptr [rbx+60h], 19930520h
0x140004152  jz      short loc_140004162
0x140004154  cmp     [rbx], r9d
0x140004157  jz      short loc_140004162
0x140004159  test    byte ptr [rdi], 20h
0x14000415c  jnz     loc_140004357
0x140004162  test    byte ptr [rbx+4], 66h
0x140004166  jz      loc_140004291
0x14000416c  cmp     [rdi+8], ebp
0x14000416f  jz      loc_140004357
0x140004175  movsxd  rcx, dword ptr [rdi+8]
0x140004179  lea     r14, cs:140000000h
0x140004180  mov     rdx, [rsi+8]
0x140004184  add     rdx, rcx
0x140004187  movzx   ecx, byte ptr [rdx]
0x14000418a  and     ecx, 0Fh
0x14000418d  movsx   rax, byte ptr [rcx+r14+7460h]
0x140004196  mov     cl, [rcx+r14+7470h]
0x14000419e  sub     rdx, rax
0x1400041a1  mov     eax, [rdx-4]
0x1400041a4  shr     eax, cl
0x1400041a6  test    eax, eax
0x1400041a8  jz      loc_140004357
0x1400041ae  cmp     [rsp+98h+arg_28], ebp
0x1400041b5  jnz     loc_140004357
0x1400041bb  test    byte ptr [rbx+4], 20h
0x1400041bf  jz      loc_14000427E
0x1400041c5  cmp     [rbx], r9d
0x1400041c8  jnz     short loc_140004232
0x1400041ca  mov     r8, [rsi+20h]; unsigned __int64
0x1400041ce  mov     rdx, rsi; struct _xDISPATCHER_CONTEXT *
0x1400041d1  mov     rcx, rdi; struct FH4::FuncInfo4 *
0x1400041d4  call    ?StateFromIp@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@_K@Z; __FrameHandler4::StateFromIp(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *,unsigned __int64)
0x1400041d9  mov     r9d, eax; int
0x1400041dc  cmp     eax, 0FFFFFFFFh
0x1400041df  jl      loc_14000437E
0x1400041e5  cmp     [rdi+8], ebp
0x1400041e8  jz      short loc_140004216
0x1400041ea  movsxd  rdx, dword ptr [rdi+8]
0x1400041ee  mov     r8, [rsi+8]
0x1400041f2  add     r8, rdx
0x1400041f5  movzx   ecx, byte ptr [r8]
0x1400041f9  and     ecx, 0Fh
0x1400041fc  movsx   rax, byte ptr [rcx+r14+7460h]
0x140004205  mov     cl, [rcx+r14+7470h]
0x14000420d  sub     r8, rax
0x140004210  mov     ebp, [r8-4]
0x140004214  shr     ebp, cl
0x140004216  cmp     r9d, ebp
0x140004219  jge     loc_14000437E
0x14000421f  mov     rcx, r15; unsigned __int64 *
0x140004222  mov     rdx, rsi; struct _xDISPATCHER_CONTEXT *
0x140004225  mov     r8, rdi; struct FH4::FuncInfo4 *
0x140004228  call    ?FrameUnwindToState@__FrameHandler4@@SAXPEA_KPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@H@Z; __FrameHandler4::FrameUnwindToState(unsigned __int64 *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *,int)
0x14000422d  jmp     loc_140004357
0x140004232  cmp     [rbx], r8d
0x140004235  jnz     short loc_14000427E
0x140004237  mov     r9d, [rbx+38h]
0x14000423b  cmp     r9d, 0FFFFFFFFh
0x14000423f  jl      loc_14000437E
0x140004245  movsxd  rcx, dword ptr [rdi+8]
0x140004249  mov     rdx, [rsi+8]
0x14000424d  add     rdx, rcx
0x140004250  movzx   ecx, byte ptr [rdx]
0x140004253  and     ecx, 0Fh
0x140004256  movsx   rax, byte ptr [rcx+r14+7460h]
0x14000425f  mov     cl, [rcx+r14+7470h]
0x140004267  sub     rdx, rax
0x14000426a  mov     eax, [rdx-4]
0x14000426d  shr     eax, cl
0x14000426f  cmp     r9d, eax
0x140004272  jge     loc_14000437E
0x140004278  mov     rcx, [rbx+28h]
0x14000427c  jmp     short loc_140004222
0x14000427e  mov     r8, rdi; struct FH4::FuncInfo4 *
0x140004281  mov     rdx, rsi; struct _xDISPATCHER_CONTEXT *
0x140004284  mov     rcx, r15; unsigned __int64 *
0x140004287  call    ?FrameUnwindToEmptyState@__FrameHandler4@@SAXPEA_KPEAU_xDISPATCHER_CONTEXT@@PEAUFuncInfo4@FH4@@@Z; __FrameHandler4::FrameUnwindToEmptyState(unsigned __int64 *,_xDISPATCHER_CONTEXT *,FH4::FuncInfo4 *)
0x14000428c  jmp     loc_140004357
0x140004291  mov     r8, [rsi+8]; unsigned __int64
0x140004295  lea     rcx, [rsp+98h+var_48]; this
0x14000429a  mov     rdx, rdi; struct FH4::FuncInfo4 *
0x14000429d  call    ??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z; FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)
0x1400042a2  cmp     [rsp+98h+var_48], ebp
0x1400042a6  jnz     short loc_1400042B1
0x1400042a8  test    byte ptr [rdi], 40h
0x1400042ab  jz      loc_140004357
0x1400042b1  cmp     [rbx], r14d
0x1400042b4  jnz     short loc_14000431E
0x1400042b6  cmp     dword ptr [rbx+18h], 3
0x1400042ba  jb      short loc_14000431E
0x1400042bc  cmp     dword ptr [rbx+20h], 19930522h
0x1400042c3  jbe     short loc_14000431E
0x1400042c5  mov     rax, [rbx+30h]
0x1400042c9  movsxd  r14, dword ptr [rax+8]
0x1400042cd  test    r14d, r14d
0x1400042d0  jz      short loc_14000431E
0x1400042d2  call    _GetThrowImageBase
0x1400042d7  mov     r10, rax
0x1400042da  add     r10, r14
0x1400042dd  jz      short loc_14000431E
0x1400042df  movzx   ecx, [rsp+98h+arg_38]
0x1400042e7  mov     r9, rsi
0x1400042ea  mov     dword ptr [rsp+98h+var_60], ecx
0x1400042ee  mov     r8, r12
0x1400042f1  mov     rcx, [rsp+98h+arg_30]
0x1400042f9  mov     rdx, r15
0x1400042fc  mov     qword ptr [rsp+98h+var_68], rcx
0x140004301  mov     rax, r10
0x140004304  mov     ecx, [rsp+98h+arg_28]
0x14000430b  mov     dword ptr [rsp+98h+var_70], ecx
0x14000430f  mov     rcx, rbx
0x140004312  mov     [rsp+98h+var_78], rdi
0x140004317  call    _guard_dispatch_icall
0x14000431c  jmp     short loc_14000435C
0x14000431e  mov     rax, [rsp+98h+arg_30]
0x140004326  mov     r9, rsi
0x140004329  mov     [rsp+98h+var_60], rax; __int64
0x14000432e  mov     r8, r12
0x140004331  mov     eax, [rsp+98h+arg_28]
0x140004338  mov     rdx, r15
0x14000433b  mov     [rsp+98h+var_68], eax; int
0x14000433f  mov     rcx, rbx; struct EHExceptionRecord *
0x140004342  mov     al, [rsp+98h+arg_38]
0x140004349  mov     [rsp+98h+var_70], al; char
0x14000434d  mov     [rsp+98h+var_78], rdi; struct FH4::FuncInfo4 *
0x140004352  call    FindHandler___FrameHandler4_
0x140004357  mov     eax, 1
0x14000435c  lea     r11, [rsp+98h+var_18]
0x140004364  mov     rbx, [r11+20h]
0x140004368  mov     rbp, [r11+28h]
0x14000436c  mov     rsi, [r11+30h]
0x140004370  mov     rdi, [r11+38h]
0x140004374  mov     rsp, r11
0x140004377  pop     r15
0x140004379  pop     r14
0x14000437b  pop     r12
0x14000437d  retn
0x14000437e  call    abort
```
