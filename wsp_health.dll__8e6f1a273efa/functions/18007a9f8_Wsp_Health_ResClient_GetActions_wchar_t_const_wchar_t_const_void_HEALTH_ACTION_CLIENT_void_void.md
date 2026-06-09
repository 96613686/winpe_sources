# Wsp::Health::ResClient::GetActions(wchar_t const *,wchar_t const *,void (*)(_HEALTH_ACTION_CLIENT *,void *),void *)

- ea: `0x18007a9f8`
- end: `0x18007ab6a`
- name: `?GetActions@ResClient@Health@Wsp@@QEAAJPEB_W0P6AXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z2@Z`
- size: `370`
- prototype: `__int64 __usercall@<rax>(Wsp::Health::ResClient *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, void (*)(struct _HEALTH_ACTION_CLIENT *, void *)@<r9>, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800798c0`

## callees

- `0x1800795b8`
- `0x18007a9f8`
- `0x18007ab70`
- `0x18007bfe4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007aa6f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007aa98`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007aa6f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007aa98`

## pseudocode

```c
__int64 __fastcall Wsp::Health::ResClient::GetActions(
        Wsp::Health::ResClient *this,
        const wchar_t *a2,
        const wchar_t *a3,
        void (*a4)(struct _HEALTH_ACTION_CLIENT *, void *),
        void *a5)
{
  signed int Connection; // ebx
  const WCHAR *v8; // rsi
  int v9; // eax
  void *v10; // r14
  const WCHAR *v11; // rbp
  Wsp::Health::ResClient *v12; // rcx
  Wsp::Health::ResClient *v13; // rcx
  const wchar_t *v14; // [rsp+70h] [rbp+18h] BYREF
  void (*v15)(struct _HEALTH_ACTION_CLIENT *, void *); // [rsp+78h] [rbp+20h] BYREF

  v15 = a4;
  v14 = a3;
  if ( !*((_QWORD *)this + 10) )
    return 2147943557LL;
  v14 = 0;
  if ( (int)Wsp::Health::ResClient::GetConnection(this) >= 0 )
  {
    v8 = 0;
    if ( CompareStringW(0x400u, 1u, &String1, -1, &String1, -1) != 2 )
      v8 = &String1;
    v9 = CompareStringW(0x400u, 1u, &String1, -1, &String1, -1);
    v10 = a5;
    v11 = 0;
    if ( v9 != 2 )
      v11 = &String1;
    LODWORD(v15) = (*((__int64 (__fastcall **)(_QWORD, const WCHAR *, const WCHAR *, void (__fastcall *)(Wsp::Health *__hidden, struct _HEALTH_ACTION_CLIENT *, void *), void *))this
                    + 10))(
                     *((_QWORD *)v14 + 2),
                     v8,
                     v11,
                     Wsp::Health::HealthGetActionsApiCallback,
                     a5);
    Connection = (int)v15;
    if ( !Wsp::Health::ResClient::ValidateOperation(v12, (unsigned int *)&v15) )
      goto LABEL_13;
    Connection = Wsp::Health::ResClient::GetConnection(this);
    if ( Connection < 0 )
      goto LABEL_15;
    LODWORD(v15) = (*((__int64 (__fastcall **)(_QWORD, const WCHAR *, const WCHAR *, void (__fastcall *)(Wsp::Health *__hidden, struct _HEALTH_ACTION_CLIENT *, void *), void *))this
                    + 10))(
                     *((_QWORD *)v14 + 2),
                     v8,
                     v11,
                     Wsp::Health::HealthGetActionsApiCallback,
                     v10);
    Connection = (int)v15;
    if ( Wsp::Health::ResClient::ValidateOperation(v13, (unsigned int *)&v15) )
    {
      LOWORD(Connection) = 110;
    }
    else
    {
LABEL_13:
      if ( Connection <= 0 )
        goto LABEL_15;
    }
    Connection = (unsigned __int16)Connection | 0x80070000;
    goto LABEL_15;
  }
  Connection = -2147024786;
LABEL_15:
  Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(&v14);
  return (unsigned int)Connection;
}

```

## disassembly

```asm
0x18007a9f8  mov     [rsp+arg_0], rbx
0x18007a9fd  mov     [rsp+arg_18], r9
0x18007aa02  mov     [rsp+arg_10], r8
0x18007aa07  push    rbp
0x18007aa08  push    rsi
0x18007aa09  push    rdi
0x18007aa0a  push    r14
0x18007aa0c  push    r15
0x18007aa0e  sub     rsp, 30h
0x18007aa12  cmp     qword ptr [rcx+50h], 0
0x18007aa17  mov     rdi, rcx
0x18007aa1a  jnz     short loc_18007AA26
0x18007aa1c  mov     eax, 80070485h
0x18007aa21  jmp     loc_18007AB58
0x18007aa26  lea     rdx, [rsp+58h+arg_10]
0x18007aa2b  mov     [rsp+58h+arg_10], 0
0x18007aa34  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x18007aa39  test    eax, eax
0x18007aa3b  jns     short loc_18007AA47
0x18007aa3d  mov     ebx, 8007006Eh
0x18007aa42  jmp     loc_18007AB4C
0x18007aa47  or      r14d, 0FFFFFFFFh
0x18007aa4b  lea     r15, String1
0x18007aa52  mov     ebx, 400h
0x18007aa57  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x18007aa5c  mov     r9d, r14d; cchCount1
0x18007aa5f  mov     [rsp+58h+lpString2], r15; lpString2
0x18007aa64  mov     r8, r15; lpString1
0x18007aa67  mov     ecx, ebx; Locale
0x18007aa69  lea     ebp, [r14+2]
0x18007aa6d  mov     edx, ebp; dwCmpFlags
0x18007aa6f  call    cs:__imp_CompareStringW
0x18007aa76  nop     dword ptr [rax+rax+00h]
0x18007aa7b  xor     esi, esi
0x18007aa7d  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x18007aa82  cmp     eax, 2
0x18007aa85  mov     [rsp+58h+lpString2], r15; lpString2
0x18007aa8a  mov     r9d, r14d; cchCount1
0x18007aa8d  mov     r8, r15; lpString1
0x18007aa90  mov     edx, ebp; dwCmpFlags
0x18007aa92  mov     ecx, ebx; Locale
0x18007aa94  cmovnz  rsi, r15
0x18007aa98  call    cs:__imp_CompareStringW
0x18007aa9f  nop     dword ptr [rax+rax+00h]
0x18007aaa4  mov     rcx, [rsp+58h+arg_10]
0x18007aaa9  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x18007aab0  mov     r14, [rsp+58h+arg_20]
0x18007aab8  xor     ebp, ebp
0x18007aaba  cmp     eax, 2
0x18007aabd  mov     [rsp+58h+lpString2], r14
0x18007aac2  mov     rax, [rdi+50h]
0x18007aac6  mov     rdx, rsi
0x18007aac9  mov     rcx, [rcx+10h]
0x18007aacd  cmovnz  rbp, r15
0x18007aad1  mov     r8, rbp
0x18007aad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007aad9  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x18007aade  mov     dword ptr [rsp+58h+arg_18], eax
0x18007aae2  mov     ebx, eax
0x18007aae4  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x18007aae9  test    al, al
0x18007aaeb  jz      short loc_18007AB3F
0x18007aaed  lea     rdx, [rsp+58h+arg_10]
0x18007aaf2  mov     rcx, rdi; void *
0x18007aaf5  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x18007aafa  mov     ebx, eax
0x18007aafc  test    eax, eax
0x18007aafe  js      short loc_18007AB4C
0x18007ab00  mov     rcx, [rsp+58h+arg_10]
0x18007ab05  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x18007ab0c  mov     rax, [rdi+50h]
0x18007ab10  mov     r8, rbp
0x18007ab13  mov     rdx, rsi
0x18007ab16  mov     [rsp+58h+lpString2], r14
0x18007ab1b  mov     rcx, [rcx+10h]
0x18007ab1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ab24  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x18007ab29  mov     dword ptr [rsp+58h+arg_18], eax
0x18007ab2d  mov     ebx, eax
0x18007ab2f  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x18007ab34  test    al, al
0x18007ab36  jz      short loc_18007AB3F
0x18007ab38  mov     ebx, 6Eh ; 'n'
0x18007ab3d  jmp     short loc_18007AB43
0x18007ab3f  test    ebx, ebx
0x18007ab41  jle     short loc_18007AB4C
0x18007ab43  movzx   ebx, bx
0x18007ab46  or      ebx, 80070000h
0x18007ab4c  lea     rcx, [rsp+58h+arg_10]
0x18007ab51  call    ??1?$RefCounted@VCHealthConnection@Health@Wsp@@@Health@Wsp@@QEAA@XZ; Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(void)
0x18007ab56  mov     eax, ebx
0x18007ab58  mov     rbx, [rsp+58h+arg_0]
0x18007ab5d  add     rsp, 30h
0x18007ab61  pop     r15
0x18007ab63  pop     r14
0x18007ab65  pop     rdi
0x18007ab66  pop     rsi
0x18007ab67  pop     rbp
0x18007ab68  retn
```
