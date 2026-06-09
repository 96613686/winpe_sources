# CPXWizardMutexLock::CPXWizardMutexLock(ushort * const,_GUID const *)

- ea: `0x180011c8c`
- end: `0x180011ddf`
- name: `??0CPXWizardMutexLock@@QEAA@QEAGPEBU_GUID@@@Z`
- size: `339`
- prototype: `CPXWizardMutexLock *__fastcall(CPXWizardMutexLock *__hidden this, unsigned __int16 *const, GUID *rguid)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cf6c`
- `0x180010ff4`

## callees

- `0x180007820`
- `0x18000a948`
- `0x1800107bc`
- `0x180011c8c`
- `0x180011e28`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011ce9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011d28`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180011d28`

## pseudocode

```c
CPXWizardMutexLock *__fastcall CPXWizardMutexLock::CPXWizardMutexLock(
        CPXWizardMutexLock *this,
        unsigned __int16 *const a2,
        GUID *rguid)
{
  __int64 v6; // rdi
  int v7; // eax
  __int64 v8; // r14
  _WORD *v9; // rax
  PVOID *v10; // rcx
  unsigned int inited; // eax

  *(_DWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  LODWORD(v6) = 0;
  if ( a2 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
  }
  v7 = v6 + 39;
  if ( !rguid )
    v7 = v6;
  if ( v7 )
  {
    v8 = (unsigned int)(v7 + 1);
    v9 = CoTaskMemAlloc(2 * v8);
    *((_QWORD *)this + 2) = v9;
    if ( v9 )
    {
      *v9 = 0;
      if ( a2 )
        StringCchCatW(*((unsigned __int16 **)this + 2), (unsigned int)v8, a2);
      if ( rguid )
        StringFromGUID2(rguid, (LPOLESTR)(*((_QWORD *)this + 2) + 2LL * (unsigned int)v6), 39);
      goto LABEL_18;
    }
    *(_DWORD *)this = -2147024882;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, 2147942414LL);
LABEL_18:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids);
      goto LABEL_18;
    }
  }
  inited = *(_DWORD *)this;
  if ( *(int *)this >= 0 )
  {
    inited = CPXWizardMutexLock::HrInitMutexState(this);
    *(_DWORD *)this = inited;
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
    WPP_SF_D(v10[2], 12, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids, inited);
  return this;
}

```

## disassembly

```asm
0x180011c8c  push    rbx
0x180011c8e  push    rbp
0x180011c8f  push    rsi
0x180011c90  push    rdi
0x180011c91  push    r12
0x180011c93  push    r14
0x180011c95  push    r15
0x180011c97  sub     rsp, 20h
0x180011c9b  xor     r15d, r15d
0x180011c9e  mov     rbp, r8
0x180011ca1  mov     [rcx], r15d
0x180011ca4  mov     rsi, rdx
0x180011ca7  mov     [rcx+8], r15
0x180011cab  mov     rbx, rcx
0x180011cae  mov     [rcx+10h], r15
0x180011cb2  mov     edi, r15d
0x180011cb5  test    rdx, rdx
0x180011cb8  jz      short loc_180011CC8
0x180011cba  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011cbe  inc     rdi
0x180011cc1  cmp     [rdx+rdi*2], r15w
0x180011cc6  jnz     short loc_180011CBE
0x180011cc8  test    rbp, rbp
0x180011ccb  lea     eax, [rdi+27h]
0x180011cce  lea     r12, WPP_GLOBAL_Control
0x180011cd5  cmovz   eax, edi
0x180011cd8  test    eax, eax
0x180011cda  jz      loc_180011D65
0x180011ce0  inc     eax
0x180011ce2  mov     r14d, eax
0x180011ce5  lea     rcx, [rax+rax]; cb
0x180011ce9  call    cs:__imp_CoTaskMemAlloc
0x180011cef  mov     [rbx+10h], rax
0x180011cf3  test    rax, rax
0x180011cf6  jz      short loc_180011D30
0x180011cf8  mov     [rax], r15w
0x180011cfc  test    rsi, rsi
0x180011cff  jz      short loc_180011D10
0x180011d01  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180011d05  mov     r8, rsi; unsigned __int16 *
0x180011d08  mov     edx, r14d; unsigned __int64
0x180011d0b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180011d10  test    rbp, rbp
0x180011d13  jz      short loc_180011D8C
0x180011d15  mov     rax, [rbx+10h]
0x180011d19  mov     r8d, 27h ; '''; cchMax
0x180011d1f  mov     ecx, edi
0x180011d21  lea     rdx, [rax+rcx*2]; lpsz
0x180011d25  mov     rcx, rbp; rguid
0x180011d28  call    cs:__imp_StringFromGUID2
0x180011d2e  jmp     short loc_180011D8C
0x180011d30  mov     dword ptr [rbx], 8007000Eh
0x180011d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d3d  cmp     rcx, r12
0x180011d40  jz      short loc_180011D93
0x180011d42  test    byte ptr [rcx+1Ch], 4
0x180011d46  jz      short loc_180011D93
0x180011d48  mov     rcx, [rcx+10h]
0x180011d4c  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180011d53  mov     edx, 0Ah
0x180011d58  mov     r9d, 8007000Eh
0x180011d5e  call    WPP_SF_D
0x180011d63  jmp     short loc_180011D8C
0x180011d65  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d6c  cmp     rcx, r12
0x180011d6f  jz      short loc_180011D93
0x180011d71  test    byte ptr [rcx+1Ch], 10h
0x180011d75  jz      short loc_180011D93
0x180011d77  mov     rcx, [rcx+10h]
0x180011d7b  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180011d82  mov     edx, 0Bh
0x180011d87  call    WPP_SF_
0x180011d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d93  mov     eax, [rbx]
0x180011d95  test    eax, eax
0x180011d97  js      short loc_180011DAA
0x180011d99  mov     rcx, rbx; this
0x180011d9c  call    ?HrInitMutexState@CPXWizardMutexLock@@AEAAJXZ; CPXWizardMutexLock::HrInitMutexState(void)
0x180011da1  mov     [rbx], eax
0x180011da3  mov     rcx, cs:WPP_GLOBAL_Control
0x180011daa  cmp     rcx, r12
0x180011dad  jz      short loc_180011DCD
0x180011daf  test    byte ptr [rcx+1Ch], 10h
0x180011db3  jz      short loc_180011DCD
0x180011db5  mov     rcx, [rcx+10h]
0x180011db9  lea     r8, WPP_6ea7f62c09ad3bf95daff1ea3fbbbf16_Traceguids
0x180011dc0  mov     edx, 0Ch
0x180011dc5  mov     r9d, eax
0x180011dc8  call    WPP_SF_D
0x180011dcd  mov     rax, rbx
0x180011dd0  add     rsp, 20h
0x180011dd4  pop     r15
0x180011dd6  pop     r14
0x180011dd8  pop     r12
0x180011dda  pop     rdi
0x180011ddb  pop     rsi
0x180011ddc  pop     rbp
0x180011ddd  pop     rbx
0x180011dde  retn
```
