# YReader::SetInputSource(tagVARIANT)

- ea: `0x100402f30`
- end: `0x100403176`
- name: `?SetInputSource@YReader@@UEAAJUtagVARIANT@@@Z`
- size: `582`
- prototype: `int(YReader *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x100401780`
- `0x1004017b0`
- `0x100402aa0`
- `0x100402f30`
- `0x10040ca10`
- `0x10040cc10`
- `0x10040dd40`
- `0x100416970`
- `0x100417060`
- `0x1004171c0`
- `0x100423830`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
__int64 __fastcall YReader::SetInputSource(YReader *this, struct tagVARIANT *a2)
{
  struct IUnknown *Unknown; // r14
  DeclEntity *v5; // rax
  struct DeclEntity *v6; // rsi
  unsigned int v7; // edx
  __int64 result; // rax
  __int64 v9; // r9
  unsigned int v10; // r8d
  struct InputSource **v11; // rdx
  struct InputSource *v12; // r14
  unsigned int v13; // eax
  __int128 v14; // [rsp+58h] [rbp-40h]
  struct InputSource *v15; // [rsp+B8h] [rbp+20h] BYREF

  if ( *((_BYTE *)this + 1753) )
    YReader::ResetStart((YReader *)((char *)this - 32));
  Unknown = Variant::getUnknown(a2, 0);
  if ( !Unknown )
    return 2147942487LL;
  *((_BYTE *)this + 1753) = 1;
  v5 = (DeclEntity *)Base::operator new(0x90u, *((struct IMalloc **)this - 3));
  if ( v5 )
    v6 = DeclEntity::DeclEntity(v5, *((struct IMalloc **)this - 3), (struct StringPtr *)&CodeStringPtr::empty, 0, 0, 0);
  else
    v6 = 0;
  DeclDoctype::InsertEntity((YReader *)((char *)this + 1224), v6);
  (*(void (__fastcall **)(struct DeclEntity *, char *))(*(_QWORD *)v6 + 48LL))(v6, (char *)this + 1680);
  v7 = *((_DWORD *)this + 110);
  if ( v7 != -1 )
    ++v7;
  if ( *((_DWORD *)this + 111) < v7 )
  {
    _mm_lfence();
    _stack<void (Scanner::*)(void),8>::grow((__int64)this + 416, v7);
  }
  result = CreateStreamInputSource(*((struct IMalloc **)this - 3), Unknown, *((_BYTE *)this + 1759), &v15);
  if ( !(_DWORD)result )
  {
    v10 = *((_DWORD *)this + 110);
    if ( *((_DWORD *)this + 111) == v10 )
    {
      _stack<void (Scanner::*)(void),8>::grow((__int64)this + 416, 0);
      v10 = *((_DWORD *)this + 110);
    }
    v11 = (struct InputSource **)(*((_QWORD *)this + 54) + 8LL * v10);
    *((_DWORD *)this + 110) = v10 + 1;
    v12 = v15;
    *v11 = v15;
    v13 = *((_DWORD *)this + 426);
    LOBYTE(v9) = v13 != dword_100450B38 || memcmp(*((const void **)this + 212), CodeStringPtr::empty, 2LL * v13);
    (*(void (__fastcall **)(struct InputSource *, char *, _QWORD, __int64))(*(_QWORD *)v12 + 32LL))(
      v12,
      (char *)this + 1696,
      *((unsigned int *)this + 451),
      v9);
    (*(void (__fastcall **)(struct InputSource *, struct DeclEntity *))(*(_QWORD *)v12 + 48LL))(v12, v6);
    Scanner::PushInputSource((YReader *)((char *)this + 8), v12);
    *((_DWORD *)this + 437) = 0;
    *((_BYTE *)this + 1758) = *((_BYTE *)this + 1757);
    *(_QWORD *)&v14 = YReader::ParseDocument;
    DWORD2(v14) = 0;
    *((_OWORD *)this + 92) = v14;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x100402f30  mov     [rsp+arg_0], rbx
0x100402f35  mov     [rsp+arg_8], rsi
0x100402f3a  push    rdi
0x100402f3b  push    r14
0x100402f3d  push    r15
0x100402f3f  sub     rsp, 80h
0x100402f46  mov     rdi, rdx
0x100402f49  mov     rbx, rcx
0x100402f4c  xor     r15d, r15d
0x100402f4f  mov     [rsp+98h+var_68], r15d
0x100402f54  cmp     [rcx+6D9h], r15b
0x100402f5b  jz      short loc_100402F66
0x100402f5d  add     rcx, 0FFFFFFFFFFFFFFE0h; this
0x100402f61  call    ?ResetStart@YReader@@AEAAXXZ; YReader::ResetStart(void)
0x100402f66  xor     edx, edx; bool
0x100402f68  mov     rcx, rdi; struct tagVARIANT *
0x100402f6b  call    ?getUnknown@Variant@@SAPEAUIUnknown@@PEAUtagVARIANT@@_N@Z; Variant::getUnknown(tagVARIANT *,bool)
0x100402f70  mov     r14, rax
0x100402f73  mov     [rsp+98h+arg_10], rax
0x100402f7b  test    rax, rax
0x100402f7e  jz      loc_100403125
0x100402f84  mov     byte ptr [rbx+6D9h], 1
0x100402f8b  mov     rdx, [rbx-18h]; struct IMalloc *
0x100402f8f  mov     ecx, 90h; dwBytes
0x100402f94  call    ??2Base@@SAPEAX_KPEAUIMalloc@@@Z; Base::operator new(unsigned __int64,IMalloc *)
0x100402f99  test    rax, rax
0x100402f9c  jz      short loc_100402FC3
0x100402f9e  mov     [rsp+98h+var_70], 0; bool
0x100402fa3  mov     [rsp+98h+var_78], r15; struct StringPtr *
0x100402fa8  xor     r9d, r9d; bool
0x100402fab  lea     r8, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x100402fb2  mov     rdx, [rbx-18h]; struct IMalloc *
0x100402fb6  mov     rcx, rax; this
0x100402fb9  call    ??0DeclEntity@@QEAA@PEAUIMalloc@@PEAUStringPtr@@_N12@Z; DeclEntity::DeclEntity(IMalloc *,StringPtr *,bool,StringPtr *,bool)
0x100402fbe  mov     rsi, rax
0x100402fc1  jmp     short loc_100402FC6
0x100402fc3  mov     rsi, r15
0x100402fc6  mov     [rsp+98h+var_50], rsi
0x100402fcb  lea     rcx, [rbx+4C8h]; this
0x100402fd2  mov     rdx, rsi; struct DeclEntity *
0x100402fd5  call    ?InsertEntity@DeclDoctype@@QEAAXPEAVDeclEntity@@@Z; DeclDoctype::InsertEntity(DeclEntity *)
0x100402fda  nop
0x100402fdb  mov     rax, [rsi]
0x100402fde  lea     rdx, [rbx+690h]
0x100402fe5  mov     rcx, rsi
0x100402fe8  mov     rax, [rax+30h]
0x100402fec  call    cs:__guard_dispatch_icall_fptr
0x100402ff2  lea     rdi, [rbx+1A0h]
0x100402ff9  mov     edx, [rdi+18h]
0x100402ffc  lea     eax, [rdx+1]
0x100402fff  cmp     eax, 1
0x100403002  cmovnb  edx, eax
0x100403005  cmp     [rdi+1Ch], edx
0x100403008  jnb     short loc_100403022
0x10040300a  lfence
0x10040300d  mov     rcx, rdi
0x100403010  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x100403015  mov     r14, [rsp+98h+arg_10]
0x10040301d  mov     rsi, [rsp+98h+var_50]
0x100403022  lea     r9, [rsp+98h+arg_18]; struct InputSource **
0x10040302a  movzx   r8d, byte ptr [rbx+6DFh]; bool
0x100403032  mov     rdx, r14; struct IUnknown *
0x100403035  mov     rcx, [rbx-18h]; struct IMalloc *
0x100403039  call    ?CreateStreamInputSource@@YAJPEAUIMalloc@@PEAUIUnknown@@_NPEAPEAVInputSource@@@Z; CreateStreamInputSource(IMalloc *,IUnknown *,bool,InputSource * *)
0x10040303e  mov     [rsp+98h+var_68], eax
0x100403042  test    eax, eax
0x100403044  jnz     loc_100403138
0x10040304a  mov     r8d, [rdi+18h]
0x10040304e  cmp     [rdi+1Ch], r8d
0x100403052  jnz     short loc_100403062
0x100403054  xor     edx, edx
0x100403056  mov     rcx, rdi
0x100403059  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x10040305e  mov     r8d, [rdi+18h]
0x100403062  mov     ecx, r8d
0x100403065  mov     rax, [rdi+10h]
0x100403069  lea     rdx, [rax+rcx*8]
0x10040306d  lea     eax, [r8+1]
0x100403071  mov     [rdi+18h], eax
0x100403074  mov     r14, [rsp+98h+arg_18]
0x10040307c  mov     [rdx], r14
0x10040307f  mov     eax, [rbx+6A8h]
0x100403085  cmp     eax, cs:dword_100450B38
0x10040308b  jnz     short loc_1004030AF
0x10040308d  mov     r8d, eax
0x100403090  add     r8, r8; Size
0x100403093  mov     rdx, cs:?empty@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040309a  mov     rcx, [rbx+6A0h]; Buf1
0x1004030a1  call    memcmp
0x1004030a6  test    eax, eax
0x1004030a8  jnz     short loc_1004030AF
0x1004030aa  xor     r9b, r9b
0x1004030ad  jmp     short loc_1004030B2
0x1004030af  mov     r9b, 1
0x1004030b2  mov     rax, [r14]
0x1004030b5  mov     r8d, [rbx+70Ch]
0x1004030bc  lea     rdx, [rbx+6A0h]
0x1004030c3  mov     rcx, r14
0x1004030c6  mov     rax, [rax+20h]
0x1004030ca  call    cs:__guard_dispatch_icall_fptr
0x1004030d0  mov     rax, [r14]
0x1004030d3  mov     rdx, rsi
0x1004030d6  mov     rcx, r14
0x1004030d9  mov     rax, [rax+30h]
0x1004030dd  call    cs:__guard_dispatch_icall_fptr
0x1004030e3  lea     rcx, [rbx+8]; this
0x1004030e7  mov     rdx, r14; struct InputSource *
0x1004030ea  call    ?PushInputSource@Scanner@@QEAAXPEAVInputSource@@@Z; Scanner::PushInputSource(InputSource *)
0x1004030ef  mov     [rbx+6D4h], r15d
0x1004030f6  movzx   eax, byte ptr [rbx+6DDh]
0x1004030fd  mov     [rbx+6DEh], al
0x100403103  lea     rax, ?ParseDocument@YReader@@AEAAXXZ; YReader::ParseDocument(void)
0x10040310a  mov     qword ptr [rsp+98h+var_40], rax
0x10040310f  mov     dword ptr [rsp+98h+var_40+8], r15d
0x100403114  movups  xmm0, [rsp+98h+var_40]
0x100403119  movups  xmmword ptr [rbx+5C0h], xmm0
0x100403120  mov     eax, r15d
0x100403123  jmp     short loc_10040312A
0x100403125  mov     eax, 80070057h
0x10040312a  mov     [rsp+98h+var_68], eax
0x10040312e  jmp     short loc_100403138
0x100403130  mov     eax, [rsp+98h+var_64]
0x100403134  mov     [rsp+98h+var_68], eax
0x100403138  lea     r11, [rsp+98h+var_18]
0x100403140  mov     rbx, [r11+20h]
0x100403144  mov     rsi, [r11+28h]
0x100403148  mov     rsp, r11
0x10040314b  pop     r15
0x10040314d  pop     r14
0x10040314f  pop     rdi
0x100403150  retn
0x100403151  mov     rcx, [rsp+98h+var_50]
0x100403156  test    rcx, rcx
0x100403159  jz      short loc_10040316C
0x10040315b  mov     rax, [rcx]
0x10040315e  mov     edx, 1
0x100403163  mov     rax, [rax]
0x100403166  call    cs:__guard_dispatch_icall_fptr
0x10040316c  mov     ecx, [rsp+98h+var_5C]; int
0x100403170  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100403175  nop
0x100439e90  push    rbp
0x100439e92  sub     rsp, 30h
0x100439e96  mov     rbp, rdx
0x100439e99  mov     [rbp+68h], rcx
0x100439e9d  lea     rdx, [rbp+3Ch]; int *
0x100439ea1  call    ?MXRExceptionFilter@@YAJPEAU_EXCEPTION_POINTERS@@PEAJ@Z; MXRExceptionFilter(_EXCEPTION_POINTERS *,long *)
0x100439ea6  nop
0x100439ea7  add     rsp, 30h
0x100439eab  pop     rbp
0x100439eac  retn
0x100439eae  push    rbp
0x100439eb0  sub     rsp, 30h
0x100439eb4  mov     rbp, rdx
0x100439eb7  mov     [rbp+70h], rcx
0x100439ebb  mov     [rbp+50h], rcx
0x100439ebf  mov     rax, [rbp+50h]
0x100439ec3  mov     rcx, [rax]
0x100439ec6  mov     [rbp+40h], rcx
0x100439eca  mov     rax, [rbp+40h]
0x100439ece  mov     eax, [rax]
0x100439ed0  cmp     eax, 0C0000005h
0x100439ed5  jz      short loc_100439F07
0x100439ed7  add     eax, 1FFFFFFFh
0x100439edc  cmp     eax, 1
0x100439edf  ja      short loc_100439EF7
0x100439ee1  mov     rax, [rbp+40h]
0x100439ee5  cmp     dword ptr [rax+18h], 1
0x100439ee9  jnz     short loc_100439EF7
0x100439eeb  mov     rax, [rbp+40h]
0x100439eef  mov     ecx, [rax+20h]
0x100439ef2  mov     [rbp+34h], ecx
0x100439ef5  jmp     short loc_100439EFE
0x100439ef7  mov     dword ptr [rbp+34h], 8000FFFFh
0x100439efe  mov     dword ptr [rbp+38h], 1
0x100439f05  jmp     short loc_100439F0E
0x100439f07  mov     dword ptr [rbp+38h], 0
0x100439f0e  mov     eax, [rbp+38h]
0x100439f11  add     rsp, 30h
0x100439f15  pop     rbp
0x100439f16  retn
```
