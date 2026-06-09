# CBcdUtils::CopyBcdEntry(_GUID const &,_GUID *)

- ea: `0x18000bd74`
- end: `0x18000be95`
- name: `?CopyBcdEntry@CBcdUtils@@QEAAJAEBU_GUID@@PEAU2@@Z`
- size: `289`
- prototype: `__int64 __fastcall(CBcdUtils *__hidden this, const struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000eb50`

## callees

- `0x1800097ec`
- `0x18000aba4`
- `0x18000bd74`
- `0x18001fd60`
- `0x18007ed40`

## import_xrefs

- `bcd!BcdCloseObject` at `0x18000be62`
- `bcd!BcdCloseObject` at `0x18000be79`
- `bcd!BcdCloseObject` at `0x18000be62`
- `bcd!BcdCloseObject` at `0x18000be79`
- `bcd!BcdOpenObject` at `0x18000bddb`
- `bcd!BcdOpenObject` at `0x18000bddb`
- `bcd!BcdQueryObject` at `0x18000be31`
- `bcd!BcdQueryObject` at `0x18000be31`
- `bcd!BcdCopyObject` at `0x18000be0f`
- `bcd!BcdCopyObject` at `0x18000be0f`

## pseudocode

```c
__int64 __fastcall CBcdUtils::CopyBcdEntry(CBcdUtils *this, const struct _GUID *a2, struct _GUID *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rcx
  signed int v7; // eax
  signed int v8; // eax
  signed int v9; // eax
  int v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  __int64 v13; // [rsp+40h] [rbp-20h] BYREF
  struct _GUID v14; // [rsp+48h] [rbp-18h] BYREF

  v14 = 0;
  v13 = 0;
  v12 = 0;
  v11 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_11;
  }
  v6 = *((_QWORD *)this + 9);
  if ( !v6 )
  {
    v5 = -2147483638;
    goto LABEL_3;
  }
  v7 = BcdOpenObject(v6, a2, &v13);
  if ( !SErrorConverter::C_NtStatus2HR(v7, &v11)
    || (v8 = BcdCopyObject(*((_QWORD *)this + 9), v13, 1, *((_QWORD *)this + 9), &v12),
        !SErrorConverter::C_NtStatus2HR(v8, &v11))
    || (v9 = BcdQueryObject(v12, 0, 0, &v14), !SErrorConverter::C_NtStatus2HR(v9, &v11)) )
  {
    v5 = v11;
    goto LABEL_3;
  }
  *a3 = v14;
  v5 = v11;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v12 )
  {
    BcdCloseObject();
    v12 = 0;
  }
  if ( v13 )
    BcdCloseObject();
  return v5;
}

```

## disassembly

```asm
0x18000bd74  push    rbp
0x18000bd76  push    rbx
0x18000bd77  push    rdi
0x18000bd78  mov     rbp, rsp
0x18000bd7b  sub     rsp, 60h
0x18000bd7f  mov     rax, cs:__security_cookie
0x18000bd86  xor     rax, rsp
0x18000bd89  mov     [rbp+var_8], rax
0x18000bd8d  mov     rbx, r8
0x18000bd90  mov     rdi, rcx
0x18000bd93  xorps   xmm0, xmm0
0x18000bd96  movups  [rbp+var_18], xmm0
0x18000bd9a  mov     [rbp+var_20], 0
0x18000bda2  mov     [rbp+var_28], 0
0x18000bdaa  mov     [rbp+var_30], 0
0x18000bdb1  test    r8, r8
0x18000bdb4  jnz     short loc_18000BDC7
0x18000bdb6  mov     ebx, 80070057h
0x18000bdbb  mov     ecx, ebx
0x18000bdbd  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000bdc2  jmp     loc_18000BE51
0x18000bdc7  mov     rcx, [rcx+48h]
0x18000bdcb  test    rcx, rcx
0x18000bdce  jnz     short loc_18000BDD7
0x18000bdd0  mov     ebx, 8000000Ah
0x18000bdd5  jmp     short loc_18000BDBB
0x18000bdd7  lea     r8, [rbp+var_20]
0x18000bddb  call    cs:__imp_BcdOpenObject
0x18000bde1  mov     ecx, eax; int
0x18000bde3  lea     rdx, [rbp+var_30]; int *
0x18000bde7  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000bdec  test    eax, eax
0x18000bdee  jnz     short loc_18000BDF5
0x18000bdf0  mov     ebx, [rbp+var_30]
0x18000bdf3  jmp     short loc_18000BDBB
0x18000bdf5  mov     rcx, [rdi+48h]
0x18000bdf9  lea     rax, [rbp+var_28]
0x18000bdfd  mov     [rsp+60h+var_40], rax
0x18000be02  mov     r9, rcx
0x18000be05  mov     r8d, 1
0x18000be0b  mov     rdx, [rbp+var_20]
0x18000be0f  call    cs:__imp_BcdCopyObject
0x18000be15  mov     ecx, eax; int
0x18000be17  lea     rdx, [rbp+var_30]; int *
0x18000be1b  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000be20  test    eax, eax
0x18000be22  jz      short loc_18000BDF0
0x18000be24  lea     r9, [rbp+var_18]
0x18000be28  xor     r8d, r8d
0x18000be2b  xor     edx, edx
0x18000be2d  mov     rcx, [rbp+var_28]
0x18000be31  call    cs:__imp_BcdQueryObject
0x18000be37  mov     ecx, eax; int
0x18000be39  lea     rdx, [rbp+var_30]; int *
0x18000be3d  call    ?C_NtStatus2HR@SErrorConverter@@SAHJPEAJ@Z; SErrorConverter::C_NtStatus2HR(long,long *)
0x18000be42  test    eax, eax
0x18000be44  jz      short loc_18000BDF0
0x18000be46  movups  xmm0, [rbp+var_18]
0x18000be4a  movdqu  xmmword ptr [rbx], xmm0
0x18000be4e  mov     ebx, [rbp+var_30]
0x18000be51  mov     ecx, ebx
0x18000be53  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000be58  nop
0x18000be59  mov     rcx, [rbp+var_28]
0x18000be5d  test    rcx, rcx
0x18000be60  jz      short loc_18000BE70
0x18000be62  call    cs:__imp_BcdCloseObject
0x18000be68  mov     [rbp+var_28], 0
0x18000be70  mov     rcx, [rbp+var_20]
0x18000be74  test    rcx, rcx
0x18000be77  jz      short loc_18000BE7F
0x18000be79  call    cs:__imp_BcdCloseObject
0x18000be7f  mov     eax, ebx
0x18000be81  mov     rcx, [rbp+var_8]
0x18000be85  xor     rcx, rsp; StackCookie
0x18000be88  call    __security_check_cookie
0x18000be8d  add     rsp, 60h
0x18000be91  pop     rdi
0x18000be92  pop     rbx
0x18000be93  pop     rbp
0x18000be94  retn
```
