# SessionDataUtil::WUOptionalSessionInfo4::CreateInstance(ulong,void const *,ulong,IUnknown *,SessionDataUtil::WUOptionalSessionInfo4 * *)

- ea: `0x140016b20`
- end: `0x140016c46`
- name: `?CreateInstance@WUOptionalSessionInfo4@SessionDataUtil@@SAJKPEBXKPEAUIUnknown@@PEAPEAV12@@Z`
- size: `294`
- prototype: `static int(unsigned int, const void *, unsigned int, struct IUnknown *, struct SessionDataUtil::WUOptionalSessionInfo4 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400170dc`
- `0x140017b48`

## callees

- `0x140002ac0`
- `0x140013cf0`
- `0x140016b20`
- `0x140016cd4`
- `0x14001ad2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionDataUtil::WUOptionalSessionInfo4::CreateInstance(
        unsigned int a1,
        const void *a2,
        unsigned int a3,
        struct IUnknown *a4,
        struct SessionDataUtil::WUOptionalSessionInfo4 **a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  SessionDataUtil::WUOptionalSessionInfo4 *v12; // rax
  SessionDataUtil::WUOptionalSessionInfo4 *v13; // rbx
  unsigned int v14; // edi
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-58h]
  _QWORD v17[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a2 )
  {
    v9 = -2147024809;
    v10 = 496;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
      (const char *)v9,
      v16);
    return v9;
  }
  if ( !a5 )
  {
    v9 = -2147467261;
    v10 = 497;
    goto LABEL_3;
  }
  v17[0] = 0;
  WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(v17);
  v12 = (SessionDataUtil::WUOptionalSessionInfo4 *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v12;
  if ( v12 )
  {
    *(_QWORD *)v12 = 0;
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 2) = 0;
  }
  else
  {
    v13 = 0;
  }
  v17[0] = v13;
  v14 = v13 == 0 ? 0x8007000E : 0;
  if ( v13 )
  {
    v14 = SessionDataUtil::WUOptionalSessionInfo4::Initialize(v13, a1, a2, a3, a4);
    if ( (v14 & 0x80000000) == 0 )
    {
      v17[0] = 0;
      *a5 = v13;
      v14 = 0;
      goto LABEL_15;
    }
    v15 = 505;
  }
  else
  {
    v15 = 500;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v15,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\SessionDataUtil.cpp",
    (const char *)v14,
    v16);
LABEL_15:
  WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(v17);
  return v14;
}

```

## disassembly

```asm
0x140016b20  push    rbx
0x140016b22  push    rbp
0x140016b23  push    rsi
0x140016b24  push    rdi
0x140016b25  push    r12
0x140016b27  push    r14
0x140016b29  push    r15
0x140016b2b  sub     rsp, 40h
0x140016b2f  mov     r12, r9
0x140016b32  mov     r15d, r8d
0x140016b35  mov     rbp, rdx
0x140016b38  mov     r14d, ecx
0x140016b3b  mov     rsi, [rsp+78h+arg_20]
0x140016b43  test    rdx, rdx
0x140016b46  jnz     short loc_140016B6D
0x140016b48  mov     ebx, 80070057h
0x140016b4d  mov     edx, 1F0h; void *
0x140016b52  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016b59  mov     r9d, ebx; char *
0x140016b5c  mov     rcx, [rsp+78h]; this
0x140016b61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016b66  mov     eax, ebx
0x140016b68  jmp     loc_140016C37
0x140016b6d  test    rsi, rsi
0x140016b70  jnz     short loc_140016B7E
0x140016b72  mov     ebx, 80004003h
0x140016b77  mov     edx, 1F1h
0x140016b7c  jmp     short loc_140016B52
0x140016b7e  mov     [rsp+78h+var_48], 0
0x140016b87  lea     rcx, [rsp+78h+var_48]
0x140016b8c  call    ?InternalRelease@?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(void)
0x140016b91  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140016b98  mov     ecx, 18h; unsigned __int64
0x140016b9d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140016ba2  mov     rbx, rax
0x140016ba5  test    rax, rax
0x140016ba8  jz      short loc_140016BC3
0x140016baa  mov     qword ptr [rax], 0
0x140016bb1  mov     qword ptr [rax+8], 0
0x140016bb9  mov     qword ptr [rax+10h], 0
0x140016bc1  jmp     short loc_140016BC5
0x140016bc3  xor     ebx, ebx
0x140016bc5  mov     [rsp+78h+var_48], rbx
0x140016bca  mov     rax, rbx
0x140016bcd  neg     rax
0x140016bd0  sbb     edi, edi
0x140016bd2  not     edi
0x140016bd4  and     edi, 8007000Eh
0x140016bda  test    rbx, rbx
0x140016bdd  jnz     short loc_140016BE6
0x140016bdf  mov     edx, 1F4h
0x140016be4  jmp     short loc_140016C07
0x140016be6  mov     qword ptr [rsp+78h+var_58], r12; int
0x140016beb  mov     r9d, r15d; unsigned int
0x140016bee  mov     r8, rbp; void *
0x140016bf1  mov     edx, r14d; unsigned int
0x140016bf4  mov     rcx, rbx; this
0x140016bf7  call    ?Initialize@WUOptionalSessionInfo4@SessionDataUtil@@AEAAJKPEBXKPEAUIUnknown@@@Z; SessionDataUtil::WUOptionalSessionInfo4::Initialize(ulong,void const *,ulong,IUnknown *)
0x140016bfc  mov     edi, eax
0x140016bfe  test    eax, eax
0x140016c00  jns     short loc_140016C1D
0x140016c02  mov     edx, 1F9h; void *
0x140016c07  mov     rcx, [rsp+78h]; this
0x140016c0c  mov     r9d, edi; char *
0x140016c0f  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x140016c16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016c1b  jmp     short loc_140016C2B
0x140016c1d  mov     [rsp+78h+var_48], 0
0x140016c26  mov     [rsi], rbx
0x140016c29  xor     edi, edi
0x140016c2b  lea     rcx, [rsp+78h+var_48]
0x140016c30  call    ?InternalRelease@?$XPtrBase@VWUOptionalSessionInfo4@SessionDataUtil@@U?$STPolicy@VWUOptionalSessionInfo4@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUOptionalSessionInfo4,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUOptionalSessionInfo4>>::InternalRelease(void)
0x140016c35  mov     eax, edi
0x140016c37  add     rsp, 40h
0x140016c3b  pop     r15
0x140016c3d  pop     r14
0x140016c3f  pop     r12
0x140016c41  pop     rdi
0x140016c42  pop     rsi
0x140016c43  pop     rbp
0x140016c44  pop     rbx
0x140016c45  retn
```
