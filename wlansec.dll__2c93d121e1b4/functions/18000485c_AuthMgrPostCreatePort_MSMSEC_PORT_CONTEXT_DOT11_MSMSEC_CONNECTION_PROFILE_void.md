# AuthMgrPostCreatePort(MSMSEC_PORT_CONTEXT *,DOT11_MSMSEC_CONNECTION_PROFILE *,void *)

- ea: `0x18000485c`
- end: `0x180004c35`
- name: `?AuthMgrPostCreatePort@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAX@Z`
- size: `985`
- prototype: `unsigned int __fastcall(struct MSMSEC_PORT_CONTEXT *, struct DOT11_MSMSEC_CONNECTION_PROFILE *, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x180004794`

## callees

- `0x180002af4`
- `0x180002c98`
- `0x18000485c`
- `0x180006738`
- `0x180006a78`
- `0x18000892c`
- `0x180008998`
- `0x1800169c0`
- `0x18002b078`
- `0x18002bb08`
- `0x18002c1cc`
- `0x180033b50`
- `0x180036c98`
- `0x18003b104`
- `0x18004232c`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180004a81`
- `MobileNetworking!ReleaseWriteLock` at `0x180004a81`
- `MobileNetworking!AcquireWriteLock` at `0x180004a12`
- `MobileNetworking!AcquireWriteLock` at `0x180004a12`

## string_xrefs

- `0x1800049fe`: `AuthMgrPostCreatePort`
- `0x180004a6d`: `AuthMgrPostCreatePort`
- `0x180004b37`: `AuthMgrPostCreatePort`

## pseudocode

```c
__int64 __fastcall AuthMgrPostCreatePort(
        struct MSMSEC_PORT_CONTEXT *a1,
        struct DOT11_MSMSEC_CONNECTION_PROFILE *a2,
        void *a3)
{
  void *v3; // r14
  PVOID *v7; // rcx
  unsigned int v8; // edi
  unsigned int updated; // eax
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  __int64 v13; // r8
  struct _GUID v14; // xmm0
  const unsigned __int16 *v15; // rdx
  _DWORD *v16; // rcx
  int v17; // eax
  int v18; // edx
  _DWORD *v19; // rcx
  int v20; // eax
  _DWORD *v21; // rcx
  struct _GUID v23; // [rsp+30h] [rbp-10h] BYREF
  void *v24; // [rsp+80h] [rbp+40h] BYREF
  void *v25; // [rsp+88h] [rbp+48h] BYREF
  void *v26; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  v25 = 0;
  v24 = 0;
  v26 = 0;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 47, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_DWORD *)a2 + 8) )
  {
    v8 = 0;
    if ( v7 == &WPP_GLOBAL_Control )
      return v8;
    if ( (*((_BYTE *)v7 + 68) & 2) != 0 )
    {
      WPP_SF_d(v7[7], 48, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, *((unsigned int *)a1 + 78));
LABEL_47:
      v7 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  updated = MSMSecCreateTimer(
              &v26,
              a3,
              (struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 320),
              a1,
              (void (*)(void *, void *))AuthMgrTimeOutFn);
  v8 = updated;
  if ( updated )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
    {
      v10 = 49;
LABEL_12:
      v11 = updated;
LABEL_26:
      WPP_SF_d(v7[7], v10, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v11);
LABEL_27:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v12 = AddHandleTableEntry(*((void **)a1 + 3), &v24);
    v8 = v12;
    if ( v12 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      {
        v3 = v24;
        goto LABEL_28;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 50, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v12);
      v3 = v24;
      goto LABEL_27;
    }
    v3 = v24;
    updated = UpdateHandleTableEntry(v24, (unsigned __int8 (*)[6])((char *)a1 + 302), a1);
    v8 = updated;
    if ( updated )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v10 = 51;
        goto LABEL_12;
      }
    }
    else
    {
      TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), ">>> Locking >>>");
      AcquireWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "AuthMgrPostCreatePort", 550);
      v13 = *((_QWORD *)a1 + 3);
      v14 = *(struct _GUID *)(v13 + 32);
      v15 = (const unsigned __int16 *)(v13 + 48);
      LODWORD(v13) = *(_DWORD *)(v13 + 2100);
      v23 = v14;
      v8 = AuthMgrCreateOneXPort(&v23, v15, v13, v3, a2, &v25);
      TraceAdapterId(*(_DWORD *)(*((_QWORD *)a1 + 3) + 2496LL), "<<< Unlocking <<<");
      ReleaseWriteLock(*((_QWORD *)a1 + 3), *((_QWORD *)a1 + 3) + 2512LL, "AuthMgrPostCreatePort", 556);
      if ( !v8 )
      {
        TracePortId(*((_DWORD *)a1 + 78), ">>> Refing >>>");
        SecMgrRefPortEx(a1, "AuthMgrPostCreatePort", 571);
        *((_QWORD *)a1 + 116) = v25;
        *((_QWORD *)a1 + 119) = v26;
        *((_DWORD *)a1 + 230) = 3;
        *((_QWORD *)a1 + 118) = v3;
        v16 = *(_DWORD **)(*((_QWORD *)a1 + 3) + 2784LL);
        if ( v16 && (*v16 & 0x200) != 0 )
          v17 = v16[32];
        else
          v17 = 5;
        *((_DWORD *)a1 + 240) = v17;
        v18 = 60;
        *((_DWORD *)a1 + 241) = 0;
        v19 = *(_DWORD **)(*((_QWORD *)a1 + 3) + 2784LL);
        if ( v19 && (*v19 & 0x400) != 0 )
          v20 = v19[33];
        else
          v20 = 60;
        *((_DWORD *)a1 + 242) = 1000 * v20;
        v21 = *(_DWORD **)(*((_QWORD *)a1 + 3) + 2784LL);
        if ( v21 && (*v21 & 0x800) != 0 )
          v18 = v21[34];
        *((_DWORD *)a1 + 243) = 1000 * v18;
        AuthMgrResetUIRespTime((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 920));
        AuthMgrResetUIRequestTime((struct MSMSEC_PORT_CONTEXT *)((char *)a1 + 920));
        goto LABEL_47;
      }
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
      {
        v10 = 52;
        v11 = v8;
        goto LABEL_26;
      }
    }
  }
LABEL_28:
  if ( v25 )
  {
    AuthMgrDestoryOneXPort(&v25);
    *((_QWORD *)a1 + 116) = 0;
  }
  else
  {
    if ( !v3 )
      goto LABEL_33;
    RemoveHandleTableEntry(&v24);
    *((_QWORD *)a1 + 118) = 0;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_33:
  if ( v26 )
  {
    MSMSecDeleteTimer(v26);
    *((_QWORD *)a1 + 119) = 0;
    goto LABEL_47;
  }
LABEL_48:
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x100) != 0 )
    WPP_SF_d(v7[7], 53, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000485c  push    rbp
0x18000485e  push    rbx
0x18000485f  push    rsi
0x180004860  push    rdi
0x180004861  push    r13
0x180004863  push    r14
0x180004865  push    r15
0x180004867  mov     rbp, rsp
0x18000486a  sub     rsp, 40h
0x18000486e  xor     r14d, r14d
0x180004871  mov     [rbp+arg_8], 0
0x180004879  mov     [rbp+arg_0], r14
0x18000487d  mov     rdi, r8
0x180004880  mov     r15, rdx
0x180004883  mov     [rbp+arg_18], 0
0x18000488b  mov     rsi, rcx
0x18000488e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004895  lea     r13, WPP_GLOBAL_Control
0x18000489c  cmp     rcx, r13
0x18000489f  jz      short loc_1800048C5
0x1800048a1  test    dword ptr [rcx+44h], 100h
0x1800048a8  jz      short loc_1800048C5
0x1800048aa  mov     rcx, [rcx+38h]
0x1800048ae  lea     edx, [r14+2Fh]
0x1800048b2  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x1800048b9  call    WPP_SF_
0x1800048be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800048c5  cmp     [r15+20h], r14d
0x1800048c9  jnz     short loc_1800048FF
0x1800048cb  xor     edi, edi
0x1800048cd  cmp     rcx, r13
0x1800048d0  jz      loc_180004C23
0x1800048d6  test    byte ptr [rcx+44h], 2
0x1800048da  jz      loc_180004BFD
0x1800048e0  mov     r9d, [rsi+138h]
0x1800048e7  lea     edx, [rdi+30h]
0x1800048ea  mov     rcx, [rcx+38h]
0x1800048ee  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x1800048f5  call    WPP_SF_d
0x1800048fa  jmp     loc_180004BF6
0x1800048ff  lea     rax, ?AuthMgrTimeOutFn@@YAXPEAX0@Z; AuthMgrTimeOutFn(void *,void *)
0x180004906  mov     r9, rsi; void *
0x180004909  lea     r8, [rsi+140h]; struct _READ_WRITE_LOCK *
0x180004910  mov     [rsp+40h+var_20], rax; void (*)(void *, void *)
0x180004915  mov     rdx, rdi; void *
0x180004918  lea     rcx, [rbp+arg_18]; void **
0x18000491c  lea     rbx, [rsi+398h]
0x180004923  call    ?MSMSecCreateTimer@@YAKPEAPEAXPEAXPEAU_READ_WRITE_LOCK@@1P6AX11@Z@Z; MSMSecCreateTimer(void * *,void *,_READ_WRITE_LOCK *,void *,void (*)(void *,void *))
0x180004928  mov     edi, eax
0x18000492a  test    eax, eax
0x18000492c  jz      short loc_180004955
0x18000492e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004935  cmp     rcx, r13
0x180004938  jz      loc_180004AC6
0x18000493e  test    byte ptr [rcx+44h], 1
0x180004942  jz      loc_180004AC6
0x180004948  mov     edx, 31h ; '1'
0x18000494d  mov     r9d, eax
0x180004950  jmp     loc_180004AAF
0x180004955  mov     rcx, [rsi+18h]; void *
0x180004959  lea     rdx, [rbp+arg_0]; void **
0x18000495d  call    ?AddHandleTableEntry@@YAKPEAXPEAPEAX@Z; AddHandleTableEntry(void *,void * *)
0x180004962  mov     edi, eax
0x180004964  test    eax, eax
0x180004966  jz      short loc_1800049A4
0x180004968  mov     rcx, cs:WPP_GLOBAL_Control
0x18000496f  cmp     rcx, r13
0x180004972  jz      short loc_18000499B
0x180004974  test    byte ptr [rcx+44h], 1
0x180004978  jz      short loc_18000499B
0x18000497a  mov     rcx, [rcx+38h]
0x18000497e  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180004985  mov     edx, 32h ; '2'
0x18000498a  mov     r9d, eax
0x18000498d  call    WPP_SF_d
0x180004992  mov     r14, [rbp+arg_0]
0x180004996  jmp     loc_180004ABF
0x18000499b  mov     r14, [rbp+arg_0]
0x18000499f  jmp     loc_180004AC6
0x1800049a4  mov     r14, [rbp+arg_0]
0x1800049a8  lea     rdx, [rsi+12Eh]; unsigned __int8 (*)[6]
0x1800049af  mov     rcx, r14; void *
0x1800049b2  mov     r8, rsi; void *
0x1800049b5  call    ?UpdateHandleTableEntry@@YAKPEAXPEAY05E0@Z; UpdateHandleTableEntry(void *,uchar (*)[6],void *)
0x1800049ba  mov     edi, eax
0x1800049bc  test    eax, eax
0x1800049be  jz      short loc_1800049E4
0x1800049c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800049c7  cmp     rcx, r13
0x1800049ca  jz      loc_180004AC6
0x1800049d0  test    byte ptr [rcx+44h], 1
0x1800049d4  jz      loc_180004AC6
0x1800049da  mov     edx, 33h ; '3'
0x1800049df  jmp     loc_18000494D
0x1800049e4  mov     rcx, [rsi+18h]
0x1800049e8  lea     rdx, aLocking; ">>> Locking >>>"
0x1800049ef  mov     ecx, [rcx+9C0h]; unsigned int
0x1800049f5  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x1800049fa  mov     rcx, [rsi+18h]
0x1800049fe  lea     r8, aAuthmgrpostcre; "AuthMgrPostCreatePort"
0x180004a05  mov     r9d, 226h
0x180004a0b  lea     rdx, [rcx+9D0h]
0x180004a12  call    cs:__imp_AcquireWriteLock
0x180004a19  nop     dword ptr [rax+rax+00h]
0x180004a1e  mov     r8, [rsi+18h]
0x180004a22  lea     rax, [rbp+arg_8]
0x180004a26  mov     [rsp+40h+var_18], rax; void **
0x180004a2b  lea     rcx, [rbp+var_10]; struct _GUID *
0x180004a2f  mov     r9, r14; void *
0x180004a32  mov     [rsp+40h+var_20], r15; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180004a37  movups  xmm0, xmmword ptr [r8+20h]
0x180004a3c  lea     rdx, [r8+30h]; unsigned __int16 *
0x180004a40  mov     r8d, [r8+834h]; unsigned int
0x180004a47  movdqu  xmmword ptr [rbp+var_10.Data1], xmm0
0x180004a4c  call    ?AuthMgrCreateOneXPort@@YAKPEAU_GUID@@PEBGKPEAXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAPEAX@Z; AuthMgrCreateOneXPort(_GUID *,ushort const *,ulong,void *,DOT11_MSMSEC_CONNECTION_PROFILE *,void * *)
0x180004a51  mov     rcx, [rsi+18h]
0x180004a55  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180004a5c  mov     edi, eax
0x180004a5e  mov     ecx, [rcx+9C0h]; unsigned int
0x180004a64  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180004a69  mov     rcx, [rsi+18h]
0x180004a6d  lea     r8, aAuthmgrpostcre; "AuthMgrPostCreatePort"
0x180004a74  mov     r9d, 22Ch
0x180004a7a  lea     rdx, [rcx+9D0h]
0x180004a81  call    cs:__imp_ReleaseWriteLock
0x180004a88  nop     dword ptr [rax+rax+00h]
0x180004a8d  test    edi, edi
0x180004a8f  jz      loc_180004B1F
0x180004a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a9c  cmp     rcx, r13
0x180004a9f  jz      short loc_180004AC6
0x180004aa1  test    byte ptr [rcx+44h], 1
0x180004aa5  jz      short loc_180004AC6
0x180004aa7  mov     edx, 34h ; '4'
0x180004aac  mov     r9d, edi
0x180004aaf  mov     rcx, [rcx+38h]
0x180004ab3  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180004aba  call    WPP_SF_d
0x180004abf  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ac6  cmp     [rbp+arg_8], 0
0x180004acb  jz      short loc_180004AE0
0x180004acd  lea     rcx, [rbp+arg_8]; void **
0x180004ad1  call    ?AuthMgrDestoryOneXPort@@YAXPEAPEAX@Z; AuthMgrDestoryOneXPort(void * *)
0x180004ad6  mov     qword ptr [rbx+8], 0
0x180004ade  jmp     short loc_180004AF6
0x180004ae0  test    r14, r14
0x180004ae3  jz      short loc_180004AFD
0x180004ae5  lea     rcx, [rbp+arg_0]; void **
0x180004ae9  call    ?RemoveHandleTableEntry@@YAKPEAPEAX@Z; RemoveHandleTableEntry(void * *)
0x180004aee  mov     qword ptr [rbx+18h], 0
0x180004af6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004afd  mov     rax, [rbp+arg_18]
0x180004b01  test    rax, rax
0x180004b04  jz      loc_180004BFD
0x180004b0a  mov     rcx, rax; void *
0x180004b0d  call    ?MSMSecDeleteTimer@@YAXPEAX@Z; MSMSecDeleteTimer(void *)
0x180004b12  mov     qword ptr [rbx+20h], 0
0x180004b1a  jmp     loc_180004BF6
0x180004b1f  mov     ecx, [rsi+138h]; unsigned int
0x180004b25  lea     rdx, aRefing; ">>> Refing >>>"
0x180004b2c  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180004b31  mov     r8d, 23Bh; int
0x180004b37  lea     rdx, aAuthmgrpostcre; "AuthMgrPostCreatePort"
0x180004b3e  mov     rcx, rsi; struct MSMSEC_PORT_CONTEXT *
0x180004b41  call    ?SecMgrRefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrRefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180004b46  mov     rax, [rbp+arg_8]
0x180004b4a  mov     [rbx+8], rax
0x180004b4e  mov     rax, [rbp+arg_18]
0x180004b52  mov     [rbx+20h], rax
0x180004b56  mov     dword ptr [rbx], 3
0x180004b5c  mov     [rbx+18h], r14
0x180004b60  mov     rax, [rsi+18h]
0x180004b64  mov     rcx, [rax+0AE0h]
0x180004b6b  test    rcx, rcx
0x180004b6e  jz      short loc_180004B80
0x180004b70  test    dword ptr [rcx], 200h
0x180004b76  jz      short loc_180004B80
0x180004b78  mov     eax, [rcx+80h]
0x180004b7e  jmp     short loc_180004B85
0x180004b80  mov     eax, 5
0x180004b85  mov     [rbx+28h], eax
0x180004b88  mov     edx, 3Ch ; '<'
0x180004b8d  mov     dword ptr [rbx+2Ch], 0
0x180004b94  mov     rax, [rsi+18h]
0x180004b98  mov     rcx, [rax+0AE0h]
0x180004b9f  test    rcx, rcx
0x180004ba2  jz      short loc_180004BB4
0x180004ba4  test    dword ptr [rcx], 400h
0x180004baa  jz      short loc_180004BB4
0x180004bac  mov     eax, [rcx+84h]
0x180004bb2  jmp     short loc_180004BB6
0x180004bb4  mov     eax, edx
0x180004bb6  imul    eax, 3E8h
0x180004bbc  mov     [rbx+30h], eax
0x180004bbf  mov     rax, [rsi+18h]
0x180004bc3  mov     rcx, [rax+0AE0h]
0x180004bca  test    rcx, rcx
0x180004bcd  jz      short loc_180004BDD
0x180004bcf  test    dword ptr [rcx], 800h
0x180004bd5  jz      short loc_180004BDD
0x180004bd7  mov     edx, [rcx+88h]
0x180004bdd  imul    eax, edx, 3E8h
0x180004be3  mov     rcx, rbx; struct MSMSEC_PORT_AUTH_CONTEXT *
0x180004be6  mov     [rbx+34h], eax
0x180004be9  call    ?AuthMgrResetUIRespTime@@YAXPEAUMSMSEC_PORT_AUTH_CONTEXT@@@Z; AuthMgrResetUIRespTime(MSMSEC_PORT_AUTH_CONTEXT *)
0x180004bee  mov     rcx, rbx; struct MSMSEC_PORT_AUTH_CONTEXT *
0x180004bf1  call    ?AuthMgrResetUIRequestTime@@YAXPEAUMSMSEC_PORT_AUTH_CONTEXT@@@Z; AuthMgrResetUIRequestTime(MSMSEC_PORT_AUTH_CONTEXT *)
0x180004bf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bfd  cmp     rcx, r13
0x180004c00  jz      short loc_180004C23
0x180004c02  test    dword ptr [rcx+44h], 100h
0x180004c09  jz      short loc_180004C23
0x180004c0b  mov     rcx, [rcx+38h]
0x180004c0f  lea     r8, WPP_4b1755f26a3a36c26101f8a1865031fa_Traceguids
0x180004c16  mov     edx, 35h ; '5'
0x180004c1b  mov     r9d, edi
0x180004c1e  call    WPP_SF_d
0x180004c23  mov     eax, edi
0x180004c25  add     rsp, 40h
0x180004c29  pop     r15
0x180004c2b  pop     r14
0x180004c2d  pop     r13
0x180004c2f  pop     rdi
0x180004c30  pop     rsi
0x180004c31  pop     rbx
0x180004c32  pop     rbp
0x180004c33  retn
```
