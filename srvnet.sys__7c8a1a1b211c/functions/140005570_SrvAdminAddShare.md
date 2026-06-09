# SrvAdminAddShare

- ea: `0x140005570`
- end: `0x140005b96`
- name: `SrvAdminAddShare`
- size: `1574`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140004d30`

## callees

- `0x1400047a0`
- `0x140005570`
- `0x140007160`
- `0x1400073d0`
- `0x140007680`
- `0x140007c60`
- `0x1400088f0`
- `0x14000a090`
- `0x14000a9c0`
- `0x140014948`
- `0x1400227cc`
- `0x140029b7c`
- `0x14002a540`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140005a5b`
- `ntoskrnl!KeBugCheckEx` at `0x14002b2ef`
- `ntoskrnl!KeBugCheckEx` at `0x140005a5b`
- `ntoskrnl!KeBugCheckEx` at `0x14002b2ef`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005b37`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140005b37`
- `ntoskrnl!ExAllocatePool2` at `0x140005707`
- `ntoskrnl!ExAllocatePool2` at `0x140005901`
- `ntoskrnl!ExAllocatePool2` at `0x140005707`
- `ntoskrnl!ExAllocatePool2` at `0x140005901`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400059ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400059bd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002b294`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400059ab`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400059bd`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002b294`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005a29`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002b2bd`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005a29`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14002b2bd`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400059e2`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400059e2`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140005606`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140005ad3`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140005606`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140005ad3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400056a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400056b7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002b273`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400056a4`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400056b7`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002b273`

## pseudocode

```c
__int64 __fastcall SrvAdminAddShare(
        __int64 a1,
        const void **a2,
        UNICODE_STRING *a3,
        const void **a4,
        const void **a5,
        unsigned __int16 *a6,
        const void **a7,
        signed int a8,
        ULONG a9,
        signed int a10,
        unsigned __int8 NewElement,
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor,
        signed int a14,
        signed int a15,
        signed int a16,
        char a17,
        signed int a18,
        _OWORD *a19)
{
  ULONG v19; // r13d
  UNICODE_STRING *p_String2; // rdi
  char v24; // r15
  ULONG v25; // eax
  int v26; // ecx
  unsigned __int64 v27; // rcx
  signed int *v28; // rbx
  int updated; // edi
  const void **v30; // r13
  char v31; // r14
  signed int v33; // ebx
  signed int *v34; // rax
  signed int *v35; // rsi
  signed __int32 v36; // ecx
  __int16 v37; // ax
  USHORT Length; // ax
  void *v39; // rcx
  __int16 v40; // ax
  void *v41; // rcx
  __int16 v42; // ax
  void *v43; // rcx
  signed int v44; // eax
  PSECURITY_DESCRIPTOR v45; // rcx
  __int16 v46; // ax
  unsigned __int64 v47; // rax
  unsigned int v48; // esi
  unsigned int *Pool2; // rax
  unsigned int *v50; // rdx
  signed __int32 v51; // ecx
  unsigned __int16 v52; // cx
  PSECURITY_DESCRIPTOR v53; // rdi
  int v54; // eax
  int v55; // eax
  _WORD *v56; // rax
  void *PoolWithTag; // rax
  __int64 v58; // rcx
  UNICODE_STRING String2; // [rsp+30h] [rbp-48h] BYREF
  _OWORD v60[3]; // [rsp+40h] [rbp-38h] BYREF

  v19 = a9;
  String2.Buffer = (PWSTR)L"*";
  NewElement = 1;
  p_String2 = a3;
  *(_QWORD *)&String2.Length = 131074;
  if ( (_BYTE)a9 != 3 || (a10 & 0x40000) == 0 )
  {
    if ( !a3 || (unsigned __int8)SrvLibIsDottedQuadAddress(a3) )
      p_String2 = &String2;
    v24 = a17;
    if ( a17
      || RtlEqualUnicodeString(p_String2, &String2, 1u)
      || (!*(_DWORD *)(a1 + 512) || (LOBYTE(a9) = 0, SrvAdminIsScopedNameEx(p_String2, &a9), (_BYTE)a9))
      && (!*(_DWORD *)(a1 + 516)
       || (v60[0] = 0u, (unsigned int)SrvAdminEvaluateServerAlias(p_String2, v60, 0, 0) == -1073741772)) )
    {
      v25 = RtlLengthSecurityDescriptor(SecurityDescriptor);
      v26 = v25 + 8 + p_String2->Length;
      a9 = v25 + 8;
      v27 = *(unsigned __int16 *)a4 + 240 + *(unsigned __int16 *)a2 + (unsigned int)*(unsigned __int16 *)a5 + v26 + 16LL;
      if ( v27 >= 0x10
        && v27 <= 0xFFFFFFFF
        && (v33 = v27, v34 = (signed int *)ExAllocatePool2(256, (unsigned int)v27, 1684095315), (v35 = v34) != 0) )
      {
        *v34 = v33;
        v34[1] = 256;
        v36 = v33 + _InterlockedExchangeAdd((volatile signed __int32 *)&xmmword_1400365F0, v33);
        if ( v33 > 0 )
        {
          do
            v54 = DWORD2(xmmword_1400365F0);
          while ( v36 > SDWORD2(xmmword_1400365F0)
               && v54 != _InterlockedCompareExchange((_DWORD *)&xmmword_1400365F0 + 2, v36, SDWORD2(xmmword_1400365F0)) );
        }
        v28 = v35 + 4;
        if ( v35 != (signed int *)-16LL )
        {
          v31 = 0;
          v35[30] = a8;
          v35[36] = a10;
          v35[39] = a14;
          v35[40] = a15;
          v35[35] = v19;
          *((_QWORD *)v35 + 7) = v35 + 4;
          v35[5] = 2;
          *((_QWORD *)v35 + 22) = a1;
          _InterlockedIncrement((volatile signed __int32 *)(a1 + 24));
          v30 = a2;
          v35[42] = *(unsigned __int8 *)(a1 + 16);
          v37 = *(_WORD *)a2;
          *((_WORD *)v35 + 13) = *(_WORD *)a2;
          *((_WORD *)v35 + 12) = v37;
          *((_QWORD *)v35 + 4) = v35 + 64;
          memmove(v35 + 64, a2[1], *(unsigned __int16 *)a2);
          Length = p_String2->Length;
          *((_WORD *)v35 + 21) = p_String2->Length;
          *((_WORD *)v35 + 20) = Length;
          v39 = (void *)(*((_QWORD *)v35 + 4) + 2 * ((unsigned __int64)*(unsigned __int16 *)a2 >> 1));
          *((_QWORD *)v35 + 6) = v39;
          memmove(v39, p_String2->Buffer, p_String2->Length);
          v40 = *(_WORD *)a4;
          *((_WORD *)v35 + 37) = *(_WORD *)a4;
          *((_WORD *)v35 + 36) = v40;
          v41 = (void *)(*((_QWORD *)v35 + 6) + 2 * ((unsigned __int64)p_String2->Length >> 1));
          *((_QWORD *)v35 + 10) = v41;
          memmove(v41, a4[1], *(unsigned __int16 *)a4);
          v42 = *(_WORD *)a5;
          *((_WORD *)v35 + 45) = *(_WORD *)a5;
          *((_WORD *)v35 + 44) = v42;
          v43 = (void *)(*((_QWORD *)v35 + 10) + 2 * ((unsigned __int64)*(unsigned __int16 *)a4 >> 1));
          *((_QWORD *)v35 + 12) = v43;
          memmove(v43, a5[1], *(unsigned __int16 *)a5);
          v44 = a16;
          v45 = SecurityDescriptor;
          *((_QWORD *)v35 + 25) = (*((unsigned __int16 *)v35 + 44) + *((_QWORD *)v35 + 12) + 7LL)
                                & 0xFFFFFFFFFFFFFFF8uLL;
          v35[41] = v44;
          *((_BYTE *)v35 + 66) = v24;
          updated = SrvAdminDuplicateSecurityDescriptor(v45);
          if ( updated )
            goto LABEL_9;
          if ( a7 )
          {
            v46 = *(_WORD *)a7;
            if ( *(_WORD *)a7 )
            {
              *((_WORD *)v35 + 53) = v46;
              *((_WORD *)v35 + 52) = v46;
              v47 = *(unsigned __int16 *)a7 + 16LL;
              if ( v47 > 0xFFFFFFFF )
              {
                _InterlockedIncrement((_DWORD *)&xmmword_1400365F0 + 1);
                *((_QWORD *)v35 + 14) = 0;
              }
              else
              {
                v48 = *(unsigned __int16 *)a7 + 16;
                Pool2 = (unsigned int *)ExAllocatePool2(256, (unsigned int)v47, 1684095315);
                v50 = Pool2;
                if ( Pool2 )
                {
                  *Pool2 = v48;
                  Pool2[1] = 256;
                  v51 = v48 + _InterlockedExchangeAdd((volatile signed __int32 *)&xmmword_1400365F0, v48);
                  if ( v48 )
                  {
                    do
                      v55 = DWORD2(xmmword_1400365F0);
                    while ( v51 > SDWORD2(xmmword_1400365F0)
                         && v55 != _InterlockedCompareExchange(
                                     (_DWORD *)&xmmword_1400365F0 + 2,
                                     v51,
                                     SDWORD2(xmmword_1400365F0)) );
                  }
                  *((_QWORD *)v28 + 12) = v50 + 4;
                  if ( v50 != (unsigned int *)-16LL )
                  {
                    memmove(v50 + 4, a7[1], *(unsigned __int16 *)a7);
                    goto LABEL_29;
                  }
                }
                else
                {
                  _InterlockedIncrement((_DWORD *)&xmmword_1400365F0 + 1);
                  *((_QWORD *)v28 + 12) = 0;
                }
              }
              updated = -1073741670;
              goto LABEL_13;
            }
          }
LABEL_29:
          if ( a6 )
          {
            v52 = *a6;
            if ( *a6 )
            {
              if ( (v28[31] & 0x100000) == 0
                || v52 < 0xAu
                || (v56 = (_WORD *)*((_QWORD *)a6 + 1), *v56 != 92)
                || v56[1] != 92
                || v56[2] == 92 )
              {
                updated = -1073741811;
                goto LABEL_13;
              }
              *((_WORD *)v28 + 101) = v52;
              *((_WORD *)v28 + 100) = v52;
              PoolWithTag = (void *)SrvNetAllocatePoolWithTag(258, *a6, 1684095315);
              *((_QWORD *)v28 + 26) = PoolWithTag;
              if ( !PoolWithTag )
              {
                updated = -1073741670;
                goto LABEL_13;
              }
              memmove(PoolWithTag, *((const void **)a6 + 1), *a6);
            }
          }
          v53 = AbsoluteSecurityDescriptor;
          if ( !AbsoluteSecurityDescriptor
            || !RtlLengthSecurityDescriptor(AbsoluteSecurityDescriptor)
            || (updated = SrvAdminDuplicateSecurityDescriptor(v53)) == 0 )
          {
            if ( a19 )
              *(_OWORD *)(v28 + 55) = *a19;
            v28[54] = a18;
            ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 200), 1u);
            ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
            if ( RtlInsertElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 408), v28 + 2, 0x28u, &NewElement) && NewElement )
            {
              if ( (unsigned __int8)RfsTableInsert(*(PEX_SPIN_LOCK *)(a1 + 72)) )
              {
                ExReleaseResourceLite((PERESOURCE)(a1 + 96));
                updated = SrvAdminUpdateProvidersOfShare(v28, 2261007);
                ExAcquireResourceExclusiveLite((PERESOURCE)(a1 + 96), 1u);
                v31 = 1;
                if ( updated >= 0 )
                {
LABEL_75:
                  v60[0] = SE_AUDITID_ADD_SHARE;
                  SrvLibAuditShareAddOrDelete(v60, v30, v28 + 6, a5);
                  if ( (v28[32] & 0x800) != 0 && !EventLoggedForABEShares )
                  {
                    EventLoggedForABEShares = 1;
                    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x1000) != 0 )
                      McTemplateK0_EtwWriteTransfer(v58, SMB2_EVENT_ABE_SHARES_PRESENT, 0);
                  }
                  goto LABEL_14;
                }
                RfsTableRemove(*(PEX_SPIN_LOCK *)(a1 + 72));
                if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 408), v28 + 2) )
                  KeBugCheckEx(
                    0x54u,
                    (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srvadmin\\sashare.c",
                    0x259u,
                    0,
                    0);
LABEL_13:
                SrvAdminDereferenceShare(v28);
LABEL_14:
                SrvAdminDereferenceShare(v28);
                if ( v31 )
                {
                  ExReleaseResourceLite((PERESOURCE)(a1 + 96));
                  ExReleaseResourceLite((PERESOURCE)(a1 + 200));
                }
                return (unsigned int)updated;
              }
              if ( !RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 408), v28 + 2) )
                KeBugCheckEx(
                  0x54u,
                  (ULONG_PTR)"onecore\\base\\fs\\remotefs\\smb\\srv\\srvadmin\\sashare.c",
                  0x239u,
                  0,
                  0);
              updated = -1073741670;
            }
            else
            {
              updated = -1073741771;
            }
            v31 = 1;
            goto LABEL_13;
          }
LABEL_9:
          if ( updated >= 0 )
            goto LABEL_75;
          goto LABEL_13;
        }
      }
      else
      {
        _InterlockedIncrement((_DWORD *)&xmmword_1400365F0 + 1);
        v28 = 0;
      }
      updated = -1073741670;
      if ( v28 )
      {
        v30 = a2;
        v31 = 0;
        goto LABEL_9;
      }
    }
    else
    {
      return (unsigned int)-1073741635;
    }
    return (unsigned int)updated;
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x140005570  mov     [rsp+arg_8], rdx
0x140005575  push    rbx
0x140005576  push    rbp
0x140005577  push    rdi
0x140005578  push    r12
0x14000557a  push    r13
0x14000557c  sub     rsp, 50h
0x140005580  mov     r13d, [rsp+78h+arg_40]
0x140005588  lea     rax, Buf2; "*"
0x14000558f  mov     [rsp+78h+String2.Buffer], rax
0x140005594  mov     r12, r9
0x140005597  mov     [rsp+78h+NewElement], 1
0x14000559f  mov     rdi, r8
0x1400055a2  mov     qword ptr [rsp+78h+String2.Length], 20002h
0x1400055ab  mov     rbx, rdx
0x1400055ae  mov     rbp, rcx
0x1400055b1  cmp     r13b, 3
0x1400055b5  jz      loc_140005AAD
0x1400055bb  mov     [rsp+78h+arg_18], r15
0x1400055c3  test    r8, r8
0x1400055c6  jz      loc_140005B22
0x1400055cc  mov     rcx, r8
0x1400055cf  call    SrvLibIsDottedQuadAddress
0x1400055d4  test    al, al
0x1400055d6  jnz     loc_140005B22
0x1400055dc  movzx   r15d, [rsp+78h+arg_80]
0x1400055e5  mov     [rsp+78h+arg_0], rsi
0x1400055ed  mov     [rsp+78h+arg_10], r14
0x1400055f5  test    r15b, r15b
0x1400055f8  jz      loc_140005B2C
0x1400055fe  mov     rcx, [rsp+78h+SecurityDescriptor]; SecurityDescriptor
0x140005606  call    cs:__imp_RtlLengthSecurityDescriptor
0x14000560d  nop     dword ptr [rax+rax+00h]
0x140005612  movzx   ecx, word ptr [rdi]
0x140005615  lea     r8d, [rax+8]
0x140005619  mov     rax, [rsp+78h+arg_20]
0x140005621  add     ecx, r8d
0x140005624  mov     [rsp+78h+arg_40], r8d
0x14000562c  movzx   edx, word ptr [rax]
0x14000562f  movzx   eax, word ptr [rbx]
0x140005632  add     edx, eax
0x140005634  movzx   eax, word ptr [r12]
0x140005639  add     ecx, edx
0x14000563b  add     eax, 0F0h
0x140005640  add     ecx, eax
0x140005642  add     rcx, 10h
0x140005646  cmp     rcx, 10h
0x14000564a  jnb     loc_1400056EA
0x140005650  lock inc dword ptr cs:xmmword_1400365F0+4
0x140005657  xor     ebx, ebx
0x140005659  mov     edi, 0C000009Ah
0x14000565e  test    rbx, rbx
0x140005661  jz      short loc_1400056C3
0x140005663  mov     r13, [rsp+78h+arg_8]
0x14000566b  xor     r14b, r14b
0x14000566e  test    edi, edi
0x140005670  js      short loc_14000568B
0x140005672  jmp     loc_14002B2FC
0x140005677  lock inc dword ptr cs:xmmword_1400365F0+4
0x14000567e  mov     qword ptr [rsi+70h], 0
0x140005686  mov     edi, 0C000009Ah
0x14000568b  mov     rcx, rbx
0x14000568e  call    SrvAdminDereferenceShare
0x140005693  mov     rcx, rbx
0x140005696  call    SrvAdminDereferenceShare
0x14000569b  test    r14b, r14b
0x14000569e  jz      short loc_1400056C3
0x1400056a0  lea     rcx, [rbp+60h]; Resource
0x1400056a4  call    cs:__imp_ExReleaseResourceLite
0x1400056ab  nop     dword ptr [rax+rax+00h]
0x1400056b0  lea     rcx, [rbp+0C8h]; Resource
0x1400056b7  call    cs:__imp_ExReleaseResourceLite
0x1400056be  nop     dword ptr [rax+rax+00h]
0x1400056c3  mov     r14, [rsp+78h+arg_10]
0x1400056cb  mov     eax, edi
0x1400056cd  mov     rsi, [rsp+78h+arg_0]
0x1400056d5  mov     r15, [rsp+78h+arg_18]
0x1400056dd  add     rsp, 50h
0x1400056e1  pop     r13
0x1400056e3  pop     r12
0x1400056e5  pop     rdi
0x1400056e6  pop     rbp
0x1400056e7  pop     rbx
0x1400056e8  retn
0x1400056ea  mov     eax, 0FFFFFFFFh
0x1400056ef  cmp     rcx, rax
0x1400056f2  ja      loc_140005650
0x1400056f8  mov     ebx, ecx
0x1400056fa  mov     r8d, 64614153h
0x140005700  mov     edx, ecx
0x140005702  mov     ecx, 100h
0x140005707  call    cs:__imp_ExAllocatePool2
0x14000570e  nop     dword ptr [rax+rax+00h]
0x140005713  mov     rsi, rax
0x140005716  test    rax, rax
0x140005719  jz      loc_140005650
0x14000571f  mov     [rax], ebx
0x140005721  mov     ecx, ebx
0x140005723  mov     dword ptr [rax+4], 100h
0x14000572a  lock xadd dword ptr cs:xmmword_1400365F0, ecx
0x140005732  add     ecx, ebx
0x140005734  test    ebx, ebx
0x140005736  jg      loc_140005A70
0x14000573c  lea     rbx, [rsi+10h]
0x140005740  test    rbx, rbx
0x140005743  jz      loc_140005659
0x140005749  mov     eax, [rsp+78h+arg_38]
0x140005750  xor     r14b, r14b
0x140005753  mov     [rbx+68h], eax
0x140005756  mov     eax, [rsp+78h+arg_48]
0x14000575d  mov     [rbx+80h], eax
0x140005763  mov     eax, [rsp+78h+arg_68]
0x14000576a  mov     [rbx+8Ch], eax
0x140005770  mov     eax, [rsp+78h+arg_70]
0x140005777  mov     [rbx+90h], eax
0x14000577d  mov     [rbx+7Ch], r13d
0x140005781  mov     [rbx+28h], rbx
0x140005785  mov     dword ptr [rbx+4], 2
0x14000578c  mov     [rbx+0A0h], rbp
0x140005793  lock inc dword ptr [rbp+18h]
0x140005797  movzx   eax, byte ptr [rbp+10h]
0x14000579b  lea     rcx, [rbx+0F0h]; void *
0x1400057a2  mov     r13, [rsp+78h+arg_8]
0x1400057aa  mov     [rbx+98h], eax
0x1400057b0  movzx   eax, word ptr [r13+0]
0x1400057b5  mov     [rbx+0Ah], ax
0x1400057b9  mov     [rbx+8], ax
0x1400057bd  mov     [rbx+10h], rcx
0x1400057c1  movzx   r8d, word ptr [r13+0]; Size
0x1400057c6  mov     rdx, [r13+8]; Src
0x1400057ca  call    memmove
0x1400057cf  movzx   eax, word ptr [rdi]
0x1400057d2  mov     [rbx+1Ah], ax
0x1400057d6  mov     [rbx+18h], ax
0x1400057da  movzx   ecx, word ptr [r13+0]
0x1400057df  mov     rax, [rbx+10h]
0x1400057e3  shr     rcx, 1
0x1400057e6  lea     rcx, [rax+rcx*2]; void *
0x1400057ea  mov     [rbx+20h], rcx
0x1400057ee  movzx   r8d, word ptr [rdi]; Size
0x1400057f2  mov     rdx, [rdi+8]; Src
0x1400057f6  call    memmove
0x1400057fb  movzx   eax, word ptr [r12]
0x140005800  mov     [rbx+3Ah], ax
0x140005804  mov     [rbx+38h], ax
0x140005808  movzx   ecx, word ptr [rdi]
0x14000580b  mov     rax, [rbx+20h]
0x14000580f  shr     rcx, 1
0x140005812  lea     rcx, [rax+rcx*2]; void *
0x140005816  mov     [rbx+40h], rcx
0x14000581a  movzx   r8d, word ptr [r12]; Size
0x14000581f  mov     rdx, [r12+8]; Src
0x140005824  call    memmove
0x140005829  mov     rdx, [rsp+78h+arg_20]
0x140005831  movzx   eax, word ptr [rdx]
0x140005834  mov     [rbx+4Ah], ax
0x140005838  mov     [rbx+48h], ax
0x14000583c  movzx   ecx, word ptr [r12]
0x140005841  mov     rax, [rbx+40h]
0x140005845  shr     rcx, 1
0x140005848  lea     rcx, [rax+rcx*2]; void *
0x14000584c  mov     [rbx+50h], rcx
0x140005850  movzx   r8d, word ptr [rdx]; Size
0x140005854  mov     rdx, [rdx+8]; Src
0x140005858  call    memmove
0x14000585d  movzx   r9d, word ptr [rbx+48h]
0x140005862  lea     rdx, [rbx+0B8h]
0x140005869  mov     r10, [rbx+50h]
0x14000586d  mov     eax, [rsp+78h+arg_78]
0x140005874  add     r10, 7
0x140005878  mov     r8d, [rsp+78h+arg_40]
0x140005880  add     r10, r9
0x140005883  mov     rcx, [rsp+78h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14000588b  and     r10, 0FFFFFFFFFFFFFFF8h
0x14000588f  xor     r9d, r9d
0x140005892  mov     [rdx], r10
0x140005895  mov     [rbx+94h], eax
0x14000589b  mov     [rbx+32h], r15b
0x14000589f  call    SrvAdminDuplicateSecurityDescriptor
0x1400058a4  mov     edi, eax
0x1400058a6  test    eax, eax
0x1400058a8  jnz     loc_14000566E
0x1400058ae  mov     rdi, [rsp+78h+arg_30]
0x1400058b6  test    rdi, rdi
0x1400058b9  jz      loc_140005954
0x1400058bf  movzx   eax, word ptr [rdi]
0x1400058c2  test    ax, ax
0x1400058c5  jz      loc_140005954
0x1400058cb  mov     [rbx+5Ah], ax
0x1400058cf  mov     [rbx+58h], ax
0x1400058d3  movzx   eax, word ptr [rdi]
0x1400058d6  add     rax, 10h
0x1400058da  cmp     rax, 10h
0x1400058de  jb      loc_140005677
0x1400058e4  mov     ecx, 0FFFFFFFFh
0x1400058e9  cmp     rax, rcx
0x1400058ec  ja      loc_140005677
0x1400058f2  mov     edx, eax
0x1400058f4  mov     ecx, 100h
0x1400058f9  mov     r8d, 64614153h
0x1400058ff  mov     esi, eax
0x140005901  call    cs:__imp_ExAllocatePool2
0x140005908  nop     dword ptr [rax+rax+00h]
0x14000590d  mov     rdx, rax
0x140005910  test    rax, rax
0x140005913  jz      loc_140005B82
0x140005919  mov     [rax], esi
0x14000591b  mov     ecx, esi
0x14000591d  mov     dword ptr [rax+4], 100h
0x140005924  lock xadd dword ptr cs:xmmword_1400365F0, ecx
0x14000592c  add     ecx, esi
0x14000592e  test    esi, esi
0x140005930  jnz     loc_140005A90
0x140005936  lea     rcx, [rdx+10h]; void *
0x14000593a  mov     [rbx+60h], rcx
0x14000593e  test    rcx, rcx
0x140005941  jz      loc_140005686
0x140005947  movzx   r8d, word ptr [rdi]; Size
0x14000594b  mov     rdx, [rdi+8]; Src
0x14000594f  call    memmove
0x140005954  mov     rdi, [rsp+78h+arg_28]
0x14000595c  test    rdi, rdi
0x14000595f  jz      short loc_14000596D
0x140005961  movzx   ecx, word ptr [rdi]
0x140005964  test    cx, cx
0x140005967  jnz     loc_140005B0B
0x14000596d  mov     rdi, [rsp+78h+AbsoluteSecurityDescriptor]
0x140005975  test    rdi, rdi
0x140005978  jnz     loc_140005AD0
0x14000597e  mov     rax, [rsp+78h+arg_90]
0x140005986  test    rax, rax
0x140005989  jz      short loc_140005995
0x14000598b  movups  xmm0, xmmword ptr [rax]
0x14000598e  movups  xmmword ptr [rbx+0DCh], xmm0
0x140005995  mov     eax, [rsp+78h+arg_88]
0x14000599c  lea     rcx, [rbp+0C8h]; Resource
0x1400059a3  mov     dl, 1; Wait
0x1400059a5  mov     [rbx+0D8h], eax
0x1400059ab  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400059b2  nop     dword ptr [rax+rax+00h]
0x1400059b7  mov     dl, 1; Wait
0x1400059b9  lea     rcx, [rbp+60h]; Resource
0x1400059bd  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400059c4  nop     dword ptr [rax+rax+00h]
0x1400059c9  lea     r9, [rsp+78h+NewElement]; NewElement
0x1400059d1  mov     r8d, 28h ; '('; BufferSize
0x1400059d7  lea     rdx, [rbx+8]; Buffer
0x1400059db  lea     rcx, [rbp+198h]; Table
0x1400059e2  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1400059e9  nop     dword ptr [rax+rax+00h]
0x1400059ee  test    rax, rax
0x1400059f1  jnz     short loc_140005A00
0x1400059f3  mov     edi, 0C0000035h
0x1400059f8  mov     r14b, 1
0x1400059fb  jmp     loc_14000568B
0x140005a00  cmp     [rsp+78h+NewElement], r14b
0x140005a08  jz      short loc_1400059F3
0x140005a0a  mov     rcx, [rbp+48h]; SpinLock
0x140005a0e  mov     rdx, rbx
0x140005a11  call    RfsTableInsert
0x140005a16  test    al, al
0x140005a18  jnz     loc_14002B26F
0x140005a1e  lea     rdx, [rbx+8]; Buffer
0x140005a22  lea     rcx, [rbp+198h]; Table
0x140005a29  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140005a30  nop     dword ptr [rax+rax+00h]
0x140005a35  test    al, al
0x140005a37  jnz     loc_14002B265
0x140005a3d  xor     r9d, r9d; BugCheckParameter3
0x140005a40  mov     [rsp+78h+BugCheckParameter4], 0; BugCheckParameter4
0x140005a49  mov     r8d, 239h; BugCheckParameter2
0x140005a4f  lea     rdx, BugCheckParameter1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140005a56  mov     ecx, 54h ; 'T'; BugCheckCode
0x140005a5b  call    cs:__imp_KeBugCheckEx
0x140005a70  mov     eax, dword ptr cs:xmmword_1400365F0+8
0x140005a76  cmp     ecx, eax
0x140005a78  jle     loc_14000573C
0x140005a7e  lock cmpxchg dword ptr cs:xmmword_1400365F0+8, ecx
0x140005a86  jnz     short loc_140005A70
0x140005a88  jmp     loc_14000573C
0x140005a90  mov     eax, dword ptr cs:xmmword_1400365F0+8
0x140005a96  cmp     ecx, eax
0x140005a98  jle     loc_140005936
0x140005a9e  lock cmpxchg dword ptr cs:xmmword_1400365F0+8, ecx
0x140005aa6  jnz     short loc_140005A90
0x140005aa8  jmp     loc_140005936
0x140005aad  test    [rsp+78h+arg_48], 40000h
0x140005ab8  jz      loc_1400055BB
0x140005abe  mov     eax, 0C000000Dh
0x140005ac3  add     rsp, 50h
0x140005ac7  pop     r13
0x140005ac9  pop     r12
0x140005acb  pop     rdi
0x140005acc  pop     rbp
0x140005acd  pop     rbx
0x140005ace  retn
0x140005ad0  mov     rcx, rdi; SecurityDescriptor
0x140005ad3  call    cs:__imp_RtlLengthSecurityDescriptor
0x140005ada  nop     dword ptr [rax+rax+00h]
0x140005adf  test    eax, eax
  ... truncated ...
```
