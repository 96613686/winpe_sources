# CCorrAPO_CapX::GetApoNotificationRegistrationInfo(APO_NOTIFICATION_DESCRIPTOR * *,ulong *)

- ea: `0x1800125b0`
- end: `0x180012652`
- name: `?GetApoNotificationRegistrationInfo@CCorrAPO_CapX@@UEAAJPEAPEAUAPO_NOTIFICATION_DESCRIPTOR@@PEAK@Z`
- size: `162`
- prototype: `__int64 __fastcall(CCorrAPO_CapX *__hidden this, struct APO_NOTIFICATION_DESCRIPTOR **, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800125b0`
- `0x180014d58`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800125dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800125dc`

## pseudocode

```c
__int64 __fastcall CCorrAPO_CapX::GetApoNotificationRegistrationInfo(CCorrAPO_CapX *this, IID **a2, unsigned int *a3)
{
  IID *v6; // rax
  IID *v7; // rbx
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 result; // rax
  __int64 v11; // rcx
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *a2 = 0;
  *a3 = 0;
  if ( !*((_QWORD *)this + 1) )
  {
    v8 = -2147467259;
    v9 = 2467;
    goto LABEL_4;
  }
  v6 = (IID *)CoTaskMemAlloc(0x20u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
    v9 = 2476;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"clientcore\\multimedia\\codecdsp\\audio\\lfxgfx\\apo\\lfxgfxapo.cpp",
      (const char *)v8,
      v12);
    return v8;
  }
  v6->Data1 = 3;
  v11 = *((_QWORD *)this + 1);
  *(_QWORD *)v6->Data4 = v11;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
  result = 0;
  v7[1] = WMALFXGFXAPO_PROPERTYSTORE_CONTEXT;
  *a2 = v7;
  *a3 = 1;
  return result;
}

```

## disassembly

```asm
0x1800125b0  push    rbx
0x1800125b2  push    rbp
0x1800125b3  push    rsi
0x1800125b4  push    rdi
0x1800125b5  sub     rsp, 28h
0x1800125b9  mov     qword ptr [rdx], 0
0x1800125c0  mov     rdi, r8
0x1800125c3  mov     dword ptr [r8], 0
0x1800125ca  mov     rsi, rdx
0x1800125cd  cmp     qword ptr [rcx+8], 0
0x1800125d2  mov     rbp, rcx
0x1800125d5  jz      short loc_180012646
0x1800125d7  mov     ecx, 20h ; ' '; cb
0x1800125dc  call    cs:__imp_CoTaskMemAlloc
0x1800125e2  mov     rbx, rax
0x1800125e5  test    rax, rax
0x1800125e8  jnz     short loc_180012613
0x1800125ea  mov     ebx, 8007000Eh
0x1800125ef  mov     edx, 9ACh; void *
0x1800125f4  mov     rcx, [rsp+48h]; this
0x1800125f9  lea     r8, aClientcoreMult; "clientcore\\multimedia\\codecdsp\\audio"...
0x180012600  mov     r9d, ebx; char *
0x180012603  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012608  mov     eax, ebx
0x18001260a  add     rsp, 28h
0x18001260e  pop     rdi
0x18001260f  pop     rsi
0x180012610  pop     rbp
0x180012611  pop     rbx
0x180012612  retn
0x180012613  mov     dword ptr [rax], 3
0x180012619  mov     rcx, [rbp+8]
0x18001261d  mov     [rax+8], rcx
0x180012621  mov     rax, [rcx]
0x180012624  mov     rax, [rax+8]
0x180012628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001262d  movups  xmm0, xmmword ptr cs:WMALFXGFXAPO_PROPERTYSTORE_CONTEXT.Data1
0x180012634  xor     eax, eax
0x180012636  movdqu  xmmword ptr [rbx+10h], xmm0
0x18001263b  mov     [rsi], rbx
0x18001263e  mov     dword ptr [rdi], 1
0x180012644  jmp     short loc_18001260A
0x180012646  mov     ebx, 80004005h
0x18001264b  mov     edx, 9A3h
0x180012650  jmp     short loc_1800125F4
```
