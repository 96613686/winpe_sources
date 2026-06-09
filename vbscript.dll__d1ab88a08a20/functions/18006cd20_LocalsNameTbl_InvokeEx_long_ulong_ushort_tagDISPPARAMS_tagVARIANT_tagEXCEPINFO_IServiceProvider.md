# LocalsNameTbl::InvokeEx(long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x18006cd20`
- end: `0x18006cf44`
- name: `?InvokeEx@LocalsNameTbl@@UEAAJJKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(LocalsNameTbl *__hidden this, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x1800016c0`
- `0x180003c40`
- `0x18001b9e0`
- `0x180031960`
- `0x180043ff4`
- `0x18006cd20`
- `0x180079436`
- `0x180079490`
- `0x18007a010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopyInd` at `0x18006ce9f`
- `OLEAUT32!__imp_VariantCopyInd` at `0x18006ce9f`

## pseudocode

```c
HRESULT __fastcall LocalsNameTbl::InvokeEx(
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
    return -2147024809;
  cNamedArgs = a5->cNamedArgs;
  if ( a5->cArgs != cNamedArgs )
    return -2147024809;
  if ( (v9 & 0xFFFFFFF0) != 0 || (v9 & 0xF) == 0 )
    return -2147024809;
  if ( (v9 & 0xFFFFFFFC) != 0 && (v9 & 3) != 0 )
    return -2147024809;
  if ( (v9 & 0xFFFFFFF3) != 0 && (v9 & 0xC) != 0 )
    return -2147024809;
  LOBYTE(v11) = 1;
  if ( (v9 & 3) == 1 )
    return -2147024809;
  if ( (v9 & 2) != 0 )
  {
    if ( (unsigned int)cNamedArgs <= 1 && (cNamedArgs != 1 || *a5->rgdispidNamedArgs == -613) )
    {
      if ( a6 )
        return VAR::GetStdVar(*((VAR **)this + 4), a6);
      else
        return 0;
    }
    return -2147024809;
  }
  rgdispidNamedArgs = a5->rgdispidNamedArgs;
  rgvarg = a5->rgvarg;
  if ( cNamedArgs > 1 )
  {
    if ( *rgdispidNamedArgs != -613 )
      return -2147352572;
    --cNamedArgs;
    ++rgdispidNamedArgs;
    ++rgvarg;
    if ( cNamedArgs > 1 )
      return -2147352572;
  }
  if ( !cNamedArgs || *rgdispidNamedArgs != -3 )
    return -2147352561;
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
  return v15;
}

```

## disassembly

```asm
0x18006cd20  push    rbx
0x18006cd22  push    rbp
0x18006cd23  push    rsi
0x18006cd24  push    rdi
0x18006cd25  push    r12
0x18006cd27  push    r14
0x18006cd29  push    r15
0x18006cd2b  sub     rsp, 70h
0x18006cd2f  mov     rax, cs:__security_cookie
0x18006cd36  xor     rax, rsp
0x18006cd39  mov     [rsp+0A8h+var_40], rax
0x18006cd3e  mov     rsi, [rsp+0A8h+arg_20]
0x18006cd46  mov     r15, rcx
0x18006cd49  mov     r14, [rsp+0A8h+arg_28]
0x18006cd51  mov     r10, [rsp+0A8h+arg_38]
0x18006cd59  movzx   edi, r9w
0x18006cd5d  mov     r9, [rsp+0A8h+arg_30]
0x18006cd65  cmp     edx, 7FFFFFFFh
0x18006cd6b  jnz     loc_18006CEFF
0x18006cd71  xor     r12d, r12d
0x18006cd74  test    r14, r14
0x18006cd77  jz      short loc_18006CD7D
0x18006cd79  mov     [r14], r12w
0x18006cd7d  test    r9, r9
0x18006cd80  jz      short loc_18006CD90
0x18006cd82  xor     edx, edx; Val
0x18006cd84  mov     rcx, r9; void *
0x18006cd87  lea     r8d, [rdx+40h]; Size
0x18006cd8b  call    memset_0
0x18006cd90  test    rsi, rsi
0x18006cd93  jz      loc_18006CEF8
0x18006cd99  mov     edx, [rsi+14h]
0x18006cd9c  cmp     [rsi+10h], edx
0x18006cd9f  jnz     loc_18006CEF8
0x18006cda5  test    edi, 0FFFFFFF0h
0x18006cdab  setz    cl
0x18006cdae  test    dil, 0Fh
0x18006cdb2  setnz   al
0x18006cdb5  test    al, cl
0x18006cdb7  jz      loc_18006CEF8
0x18006cdbd  test    edi, 0FFFFFFFCh
0x18006cdc3  movzx   r8d, di
0x18006cdc7  setnz   cl
0x18006cdca  and     r8w, 3
0x18006cdcf  setnz   al
0x18006cdd2  test    al, cl
0x18006cdd4  jnz     loc_18006CEF8
0x18006cdda  test    edi, 0FFFFFFF3h
0x18006cde0  setnz   cl
0x18006cde3  test    dil, 0Ch
0x18006cde7  setnz   al
0x18006cdea  test    al, cl
0x18006cdec  jnz     loc_18006CEF8
0x18006cdf2  mov     ebx, 1
0x18006cdf7  cmp     r8w, bx
0x18006cdfb  jz      loc_18006CEF8
0x18006ce01  test    dil, 2
0x18006ce05  jz      short loc_18006CE3E
0x18006ce07  cmp     edx, ebx
0x18006ce09  ja      loc_18006CEF8
0x18006ce0f  jnz     short loc_18006CE21
0x18006ce11  mov     rax, [rsi+8]
0x18006ce15  cmp     dword ptr [rax], 0FFFFFD9Bh
0x18006ce1b  jnz     loc_18006CEF8
0x18006ce21  test    r14, r14
0x18006ce24  jnz     short loc_18006CE2D
0x18006ce26  xor     eax, eax
0x18006ce28  jmp     loc_18006CF27
0x18006ce2d  mov     rcx, [r15+20h]; this
0x18006ce31  mov     rdx, r14; struct tagVARIANT *
0x18006ce34  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x18006ce39  jmp     loc_18006CF27
0x18006ce3e  mov     rax, [rsi+8]
0x18006ce42  mov     rcx, [rsi]
0x18006ce45  cmp     edx, ebx
0x18006ce47  jle     short loc_18006CE69
0x18006ce49  cmp     dword ptr [rax], 0FFFFFD9Bh
0x18006ce4f  jnz     short loc_18006CE5F
0x18006ce51  dec     edx
0x18006ce53  add     rax, 4
0x18006ce57  add     rcx, 18h
0x18006ce5b  cmp     edx, ebx
0x18006ce5d  jle     short loc_18006CE69
0x18006ce5f  mov     eax, 80020004h
0x18006ce64  jmp     loc_18006CF27
0x18006ce69  test    edx, edx
0x18006ce6b  jz      loc_18006CEF1
0x18006ce71  cmp     dword ptr [rax], 0FFFFFFFDh
0x18006ce74  jnz     short loc_18006CEF1
0x18006ce76  test    dil, 8
0x18006ce7a  jz      short loc_18006CE88
0x18006ce7c  not     dil
0x18006ce7f  movzx   ebx, dil
0x18006ce83  shr     ebx, 1
0x18006ce85  and     ebx, 2
0x18006ce88  xorps   xmm0, xmm0
0x18006ce8b  xor     eax, eax
0x18006ce8d  mov     rdx, rcx; pvargSrc
0x18006ce90  mov     qword ptr [rsp+0A8h+pvarDest+10h], rax
0x18006ce95  lea     rcx, [rsp+0A8h+pvarDest]; pvarDest
0x18006ce9a  movups  xmmword ptr [rsp+0A8h+pvarDest], xmm0
0x18006ce9f  call    cs:__imp_VariantCopyInd
0x18006cea6  nop     dword ptr [rax+rax+00h]
0x18006ceab  mov     edi, eax
0x18006cead  test    eax, eax
0x18006ceaf  js      short loc_18006CEED
0x18006ceb1  call    ?GetGc@GcContext@@SAPEAV1@XZ; GcContext::GetGc(void)
0x18006ceb6  lea     rcx, [rsp+0A8h+pvarDest]; this
0x18006cebb  mov     rsi, rax
0x18006cebe  mov     ebp, [rax+18h]
0x18006cec1  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x18006cec6  mov     edi, eax
0x18006cec8  test    eax, eax
0x18006ceca  js      short loc_18006CEE3
0x18006cecc  mov     rdx, [r15+20h]; struct VAR *
0x18006ced0  lea     r8, [rsp+0A8h+pvarDest]; struct VAR *
0x18006ced5  mov     rcx, [r15+10h]; struct CSession *
0x18006ced9  mov     r9d, ebx; unsigned int
0x18006cedc  call    ?AssignVar@@YAJPEAVCSession@@PEAVVAR@@1K@Z; AssignVar(CSession *,VAR *,VAR *,ulong)
0x18006cee1  mov     edi, eax
0x18006cee3  mov     edx, ebp; int
0x18006cee5  mov     rcx, rsi; this
0x18006cee8  call    ?FreeToMark@GcContext@@QEAAXJ@Z; GcContext::FreeToMark(long)
0x18006ceed  mov     eax, edi
0x18006ceef  jmp     short loc_18006CF27
0x18006cef1  mov     eax, 8002000Fh
0x18006cef6  jmp     short loc_18006CF27
0x18006cef8  mov     eax, 80070057h
0x18006cefd  jmp     short loc_18006CF27
0x18006ceff  mov     rcx, [rcx+18h]
0x18006cf03  mov     [rsp+0A8h+var_70], r10
0x18006cf08  mov     [rsp+0A8h+var_78], r9
0x18006cf0d  movzx   r9d, di
0x18006cf11  mov     [rsp+0A8h+var_80], r14
0x18006cf16  mov     rax, [rcx]
0x18006cf19  mov     [rsp+0A8h+var_88], rsi
0x18006cf1e  mov     rax, [rax+40h]
0x18006cf22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf27  mov     rcx, [rsp+0A8h+var_40]
0x18006cf2c  xor     rcx, rsp; StackCookie
0x18006cf2f  call    __security_check_cookie
0x18006cf34  add     rsp, 70h
0x18006cf38  pop     r15
0x18006cf3a  pop     r14
0x18006cf3c  pop     r12
0x18006cf3e  pop     rdi
0x18006cf3f  pop     rsi
0x18006cf40  pop     rbp
0x18006cf41  pop     rbx
0x18006cf42  retn
```
