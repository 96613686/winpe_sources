# LocalsNameTbl::InvokeEx(long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x18006abd0`
- end: `0x18006ade9`
- name: `?InvokeEx@LocalsNameTbl@@UEAAJJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `537`
- prototype: `__int64 __fastcall(LocalsNameTbl *__hidden this, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x180005e00`
- `0x180020a50`
- `0x180027e00`
- `0x18002d270`
- `0x180042974`
- `0x18006abd0`
- `0x180076746`
- `0x1800767a0`
- `0x180077010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x18006ad4b`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18006ad4b`

## pseudocode

```c
__int64 __fastcall LocalsNameTbl::InvokeEx(
        LocalsNameTbl *this,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        struct tagDISPPARAMS *a5,
        struct tagVARIANT *a6,
        struct tagEXCEPINFO *a7,
        struct IServiceProvider *a8)
{
  int v9; // edi
  signed int cNamedArgs; // edx
  int v11; // ebx
  DISPID *rgdispidNamedArgs; // rax
  VARIANTARG *rgvarg; // rcx
  HRESULT v15; // edi
  struct GcContext *Gc; // rsi
  int v17; // ebp
  VARIANT pvarDest; // [rsp+50h] [rbp-58h] BYREF

  v9 = a4;
  if ( (_DWORD)a2 != 0x7FFFFFFF )
    return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *))(**((_QWORD **)this + 3) + 64LL))(
             *((_QWORD *)this + 3),
             a2,
             a3,
             a4,
             a5,
             a6,
             a7,
             a8);
  if ( a6 )
    a6->vt = 0;
  if ( a7 )
    memset_0(a7, 0, sizeof(struct tagEXCEPINFO));
  if ( !a5 )
    return 2147942487LL;
  cNamedArgs = a5->cNamedArgs;
  if ( a5->cArgs != cNamedArgs )
    return 2147942487LL;
  if ( (v9 & 0xFFFFFFF0) != 0 || (v9 & 0xF) == 0 )
    return 2147942487LL;
  if ( (v9 & 0xFFFFFFFC) != 0 && (v9 & 3) != 0 )
    return 2147942487LL;
  if ( (v9 & 0xFFFFFFF3) != 0 && (v9 & 0xC) != 0 )
    return 2147942487LL;
  LOBYTE(v11) = 1;
  if ( (v9 & 3) == 1 )
    return 2147942487LL;
  if ( (v9 & 2) != 0 )
  {
    if ( (unsigned int)cNamedArgs <= 1 && (cNamedArgs != 1 || *a5->rgdispidNamedArgs == -613) )
    {
      if ( a6 )
        return VAR::GetStdVar(*((VAR **)this + 4), a6);
      else
        return 0;
    }
    return 2147942487LL;
  }
  rgdispidNamedArgs = a5->rgdispidNamedArgs;
  rgvarg = a5->rgvarg;
  if ( cNamedArgs > 1 )
  {
    if ( *rgdispidNamedArgs != -613 )
      return 2147614724LL;
    --cNamedArgs;
    ++rgdispidNamedArgs;
    ++rgvarg;
    if ( cNamedArgs > 1 )
      return 2147614724LL;
  }
  if ( !cNamedArgs || *rgdispidNamedArgs != -3 )
    return 2147614735LL;
  if ( (v9 & 8) != 0 )
    v11 = ((unsigned __int8)~(_BYTE)v9 >> 1) & 2;
  memset(&pvarDest, 0, sizeof(pvarDest));
  v15 = VariantCopyInd(&pvarDest, rgvarg);
  if ( v15 >= 0 )
  {
    Gc = GcContext::GetGc();
    v17 = *((_DWORD *)Gc + 6);
    v15 = VAR::Import((VAR *)&pvarDest);
    if ( v15 >= 0 )
      v15 = AssignVar(*((struct CSession **)this + 2), *((VARIANTARG **)this + 4), (struct VAR **)&pvarDest, v11);
    GcContext::FreeToMark(Gc, v17);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18006abd0  push    rbx
0x18006abd2  push    rbp
0x18006abd3  push    rsi
0x18006abd4  push    rdi
0x18006abd5  push    r12
0x18006abd7  push    r14
0x18006abd9  push    r15
0x18006abdb  sub     rsp, 70h
0x18006abdf  mov     rax, cs:__security_cookie
0x18006abe6  xor     rax, rsp
0x18006abe9  mov     [rsp+0A8h+var_40], rax
0x18006abee  mov     rsi, [rsp+0A8h+arg_20]
0x18006abf6  mov     r15, rcx
0x18006abf9  mov     r14, [rsp+0A8h+arg_28]
0x18006ac01  mov     r10, [rsp+0A8h+arg_38]
0x18006ac09  movzx   edi, r9w
0x18006ac0d  mov     r9, [rsp+0A8h+arg_30]
0x18006ac15  cmp     edx, 7FFFFFFFh
0x18006ac1b  jnz     loc_18006ADA5
0x18006ac21  xor     r12d, r12d
0x18006ac24  test    r14, r14
0x18006ac27  jz      short loc_18006AC2D
0x18006ac29  mov     [r14], r12w
0x18006ac2d  test    r9, r9
0x18006ac30  jz      short loc_18006AC40
0x18006ac32  xor     edx, edx; Val
0x18006ac34  mov     rcx, r9; void *
0x18006ac37  lea     r8d, [rdx+40h]; Size
0x18006ac3b  call    memset_0
0x18006ac40  test    rsi, rsi
0x18006ac43  jz      loc_18006AD9E
0x18006ac49  mov     edx, [rsi+14h]
0x18006ac4c  cmp     [rsi+10h], edx
0x18006ac4f  jnz     loc_18006AD9E
0x18006ac55  test    edi, 0FFFFFFF0h
0x18006ac5b  setz    cl
0x18006ac5e  test    dil, 0Fh
0x18006ac62  setnz   al
0x18006ac65  test    al, cl
0x18006ac67  jz      loc_18006AD9E
0x18006ac6d  test    edi, 0FFFFFFFCh
0x18006ac73  movzx   r8d, di
0x18006ac77  setnz   cl
0x18006ac7a  and     r8w, 3
0x18006ac7f  setnz   al
0x18006ac82  test    al, cl
0x18006ac84  jnz     loc_18006AD9E
0x18006ac8a  test    edi, 0FFFFFFF3h
0x18006ac90  setnz   cl
0x18006ac93  test    dil, 0Ch
0x18006ac97  setnz   al
0x18006ac9a  test    al, cl
0x18006ac9c  jnz     loc_18006AD9E
0x18006aca2  mov     ebx, 1
0x18006aca7  cmp     r8w, bx
0x18006acab  jz      loc_18006AD9E
0x18006acb1  test    dil, 2
0x18006acb5  jz      short loc_18006ACEE
0x18006acb7  cmp     edx, ebx
0x18006acb9  ja      loc_18006AD9E
0x18006acbf  jnz     short loc_18006ACD1
0x18006acc1  mov     rax, [rsi+8]
0x18006acc5  cmp     dword ptr [rax], 0FFFFFD9Bh
0x18006accb  jnz     loc_18006AD9E
0x18006acd1  test    r14, r14
0x18006acd4  jnz     short loc_18006ACDD
0x18006acd6  xor     eax, eax
0x18006acd8  jmp     loc_18006ADCD
0x18006acdd  mov     rcx, [r15+20h]; this
0x18006ace1  mov     rdx, r14; struct tagVARIANT *
0x18006ace4  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x18006ace9  jmp     loc_18006ADCD
0x18006acee  mov     rax, [rsi+8]
0x18006acf2  mov     rcx, [rsi]
0x18006acf5  cmp     edx, ebx
0x18006acf7  jle     short loc_18006AD19
0x18006acf9  cmp     dword ptr [rax], 0FFFFFD9Bh
0x18006acff  jnz     short loc_18006AD0F
0x18006ad01  dec     edx
0x18006ad03  add     rax, 4
0x18006ad07  add     rcx, 18h
0x18006ad0b  cmp     edx, ebx
0x18006ad0d  jle     short loc_18006AD19
0x18006ad0f  mov     eax, 80020004h
0x18006ad14  jmp     loc_18006ADCD
0x18006ad19  test    edx, edx
0x18006ad1b  jz      short loc_18006AD97
0x18006ad1d  cmp     dword ptr [rax], 0FFFFFFFDh
0x18006ad20  jnz     short loc_18006AD97
0x18006ad22  test    dil, 8
0x18006ad26  jz      short loc_18006AD34
0x18006ad28  not     dil
0x18006ad2b  movzx   ebx, dil
0x18006ad2f  shr     ebx, 1
0x18006ad31  and     ebx, 2
0x18006ad34  xorps   xmm0, xmm0
0x18006ad37  xor     eax, eax
0x18006ad39  mov     rdx, rcx; pvargSrc
0x18006ad3c  mov     qword ptr [rsp+0A8h+pvarDest+10h], rax
0x18006ad41  lea     rcx, [rsp+0A8h+pvarDest]; pvarDest
0x18006ad46  movups  xmmword ptr [rsp+0A8h+pvarDest], xmm0
0x18006ad4b  call    cs:__imp_VariantCopyInd
0x18006ad51  mov     edi, eax
0x18006ad53  test    eax, eax
0x18006ad55  js      short loc_18006AD93
0x18006ad57  call    ?GetGc@GcContext@@SAPEAV1@XZ; GcContext::GetGc(void)
0x18006ad5c  lea     rcx, [rsp+0A8h+pvarDest]; this
0x18006ad61  mov     rsi, rax
0x18006ad64  mov     ebp, [rax+18h]
0x18006ad67  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x18006ad6c  mov     edi, eax
0x18006ad6e  test    eax, eax
0x18006ad70  js      short loc_18006AD89
0x18006ad72  mov     rdx, [r15+20h]; struct VAR *
0x18006ad76  lea     r8, [rsp+0A8h+pvarDest]; struct VAR *
0x18006ad7b  mov     rcx, [r15+10h]; struct CSession *
0x18006ad7f  mov     r9d, ebx; unsigned int
0x18006ad82  call    ?AssignVar@@YAJPEAVCSession@@PEAVVAR@@1K@Z; AssignVar(CSession *,VAR *,VAR *,ulong)
0x18006ad87  mov     edi, eax
0x18006ad89  mov     edx, ebp; int
0x18006ad8b  mov     rcx, rsi; this
0x18006ad8e  call    ?FreeToMark@GcContext@@QEAAXJ@Z; GcContext::FreeToMark(long)
0x18006ad93  mov     eax, edi
0x18006ad95  jmp     short loc_18006ADCD
0x18006ad97  mov     eax, 8002000Fh
0x18006ad9c  jmp     short loc_18006ADCD
0x18006ad9e  mov     eax, 80070057h
0x18006ada3  jmp     short loc_18006ADCD
0x18006ada5  mov     rcx, [rcx+18h]
0x18006ada9  mov     [rsp+0A8h+var_70], r10
0x18006adae  mov     [rsp+0A8h+var_78], r9
0x18006adb3  movzx   r9d, di
0x18006adb7  mov     [rsp+0A8h+var_80], r14
0x18006adbc  mov     rax, [rcx]
0x18006adbf  mov     [rsp+0A8h+var_88], rsi
0x18006adc4  mov     rax, [rax+40h]
0x18006adc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006adcd  mov     rcx, [rsp+0A8h+var_40]
0x18006add2  xor     rcx, rsp; StackCookie
0x18006add5  call    __security_check_cookie
0x18006adda  add     rsp, 70h
0x18006adde  pop     r15
0x18006ade0  pop     r14
0x18006ade2  pop     r12
0x18006ade4  pop     rdi
0x18006ade5  pop     rsi
0x18006ade6  pop     rbp
0x18006ade7  pop     rbx
0x18006ade8  retn
```
