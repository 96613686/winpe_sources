# Wsp::Health::ResClient::GetActions(wchar_t const *,wchar_t const *,void (*)(_HEALTH_ACTION_CLIENT *,void *),void *)

- ea: `0x180078a60`
- end: `0x180078bc5`
- name: `?GetActions@ResClient@Health@Wsp@@QEAAJPEB_W0P6AXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z2@Z`
- size: `357`
- prototype: `__int64 __usercall@<rax>(Wsp::Health::ResClient *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, void (*)(struct _HEALTH_ACTION_CLIENT *, void *)@<r9>, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800779fc`

## callees

- `0x180077704`
- `0x180078a60`
- `0x180078bcc`
- `0x180079eac`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180078ad7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180078afa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180078ad7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180078afa`

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
0x180078a60  mov     [rsp+arg_0], rbx
0x180078a65  mov     [rsp+arg_18], r9
0x180078a6a  mov     [rsp+arg_10], r8
0x180078a6f  push    rbp
0x180078a70  push    rsi
0x180078a71  push    rdi
0x180078a72  push    r14
0x180078a74  push    r15
0x180078a76  sub     rsp, 30h
0x180078a7a  cmp     qword ptr [rcx+50h], 0
0x180078a7f  mov     rdi, rcx
0x180078a82  jnz     short loc_180078A8E
0x180078a84  mov     eax, 80070485h
0x180078a89  jmp     loc_180078BB4
0x180078a8e  lea     rdx, [rsp+58h+arg_10]
0x180078a93  mov     [rsp+58h+arg_10], 0
0x180078a9c  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x180078aa1  test    eax, eax
0x180078aa3  jns     short loc_180078AAF
0x180078aa5  mov     ebx, 8007006Eh
0x180078aaa  jmp     loc_180078BA8
0x180078aaf  or      r14d, 0FFFFFFFFh
0x180078ab3  lea     r15, String1
0x180078aba  mov     ebx, 400h
0x180078abf  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180078ac4  mov     r9d, r14d; cchCount1
0x180078ac7  mov     [rsp+58h+lpString2], r15; lpString2
0x180078acc  mov     r8, r15; lpString1
0x180078acf  mov     ecx, ebx; Locale
0x180078ad1  lea     ebp, [r14+2]
0x180078ad5  mov     edx, ebp; dwCmpFlags
0x180078ad7  call    cs:__imp_CompareStringW
0x180078add  xor     esi, esi
0x180078adf  mov     [rsp+58h+cchCount2], r14d; cchCount2
0x180078ae4  cmp     eax, 2
0x180078ae7  mov     [rsp+58h+lpString2], r15; lpString2
0x180078aec  mov     r9d, r14d; cchCount1
0x180078aef  mov     r8, r15; lpString1
0x180078af2  mov     edx, ebp; dwCmpFlags
0x180078af4  mov     ecx, ebx; Locale
0x180078af6  cmovnz  rsi, r15
0x180078afa  call    cs:__imp_CompareStringW
0x180078b00  mov     rcx, [rsp+58h+arg_10]
0x180078b05  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x180078b0c  mov     r14, [rsp+58h+arg_20]
0x180078b14  xor     ebp, ebp
0x180078b16  cmp     eax, 2
0x180078b19  mov     [rsp+58h+lpString2], r14
0x180078b1e  mov     rax, [rdi+50h]
0x180078b22  mov     rdx, rsi
0x180078b25  mov     rcx, [rcx+10h]
0x180078b29  cmovnz  rbp, r15
0x180078b2d  mov     r8, rbp
0x180078b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b35  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x180078b3a  mov     dword ptr [rsp+58h+arg_18], eax
0x180078b3e  mov     ebx, eax
0x180078b40  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x180078b45  test    al, al
0x180078b47  jz      short loc_180078B9B
0x180078b49  lea     rdx, [rsp+58h+arg_10]
0x180078b4e  mov     rcx, rdi; void *
0x180078b51  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x180078b56  mov     ebx, eax
0x180078b58  test    eax, eax
0x180078b5a  js      short loc_180078BA8
0x180078b5c  mov     rcx, [rsp+58h+arg_10]
0x180078b61  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x180078b68  mov     rax, [rdi+50h]
0x180078b6c  mov     r8, rbp
0x180078b6f  mov     rdx, rsi
0x180078b72  mov     [rsp+58h+lpString2], r14
0x180078b77  mov     rcx, [rcx+10h]
0x180078b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078b80  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x180078b85  mov     dword ptr [rsp+58h+arg_18], eax
0x180078b89  mov     ebx, eax
0x180078b8b  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x180078b90  test    al, al
0x180078b92  jz      short loc_180078B9B
0x180078b94  mov     ebx, 6Eh ; 'n'
0x180078b99  jmp     short loc_180078B9F
0x180078b9b  test    ebx, ebx
0x180078b9d  jle     short loc_180078BA8
0x180078b9f  movzx   ebx, bx
0x180078ba2  or      ebx, 80070000h
0x180078ba8  lea     rcx, [rsp+58h+arg_10]
0x180078bad  call    ??1?$RefCounted@VCHealthConnection@Health@Wsp@@@Health@Wsp@@QEAA@XZ; Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(void)
0x180078bb2  mov     eax, ebx
0x180078bb4  mov     rbx, [rsp+58h+arg_0]
0x180078bb9  add     rsp, 30h
0x180078bbd  pop     r15
0x180078bbf  pop     r14
0x180078bc1  pop     rdi
0x180078bc2  pop     rsi
0x180078bc3  pop     rbp
0x180078bc4  retn
```
