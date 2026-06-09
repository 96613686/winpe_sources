# SetProviderStatusWorker(void *)

- ea: `0x18003891c`
- end: `0x180038c48`
- name: `?SetProviderStatusWorker@@YAKPEAX@Z`
- size: `812`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x180038fa0`

## callees

- `0x180010b74`
- `0x180018138`
- `0x180018dfc`
- `0x18001d9a0`
- `0x18003891c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003893f`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038bdc`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x18003893f`
- `api-ms-win-crt-private-l1-1-0!_set_se_translator` at `0x180038bdc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180038c18`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180038c18`

## string_xrefs

- `0x180038967`: `W32TmServiceMain: SetProviderStatusWorker`
- `0x180038a0c`: `Couldn't remove provider from list: %s\n`
- `0x180038b08`: `Systerm stratum is not updated due to new stratum (%d) is superior to the system stratum stratum (%d).\n`
- `0x180038ad9`: `Systerm stratum is not updated due to new stratum (%d) is NOT superior to this provider's stratum (%d).\n`
- `0x180038b36`: `***System stratum updated***, %d --> %d\n`
- `0x180038b6b`: `System stratum not updated: %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall SetProviderStatusWorker(unsigned int *a1)
{
  int v2; // edi
  __int64 i; // r14
  unsigned __int16 *v4; // rax
  __int64 v5; // rdx
  int v6; // r8d
  int v7; // ecx
  char v8; // r15
  unsigned int v9; // eax
  unsigned int v10; // ecx
  __int64 j; // r14
  unsigned int v12; // eax
  char v13; // al
  int *v14; // rax
  void *v15; // rcx
  __int64 v17; // [rsp+98h] [rbp+10h]

  v17 = _set_se_translator(SeTransFunc);
  v2 = 0;
  if ( (unsigned __int8)FileLogAllowEntry(64) )
    FileLogAdd(L"W32TmServiceMain: SetProviderStatusWorker");
  for ( i = *(_QWORD *)qword_1800A42F0; ; i = *(_QWORD *)(i + 24) )
  {
    if ( !i )
    {
      if ( (unsigned __int8)FileLogAllowEntry(64) )
        FileLogAppend(L"provider not found.\n");
      v2 = -2147024809;
      goto LABEL_54;
    }
    v4 = (unsigned __int16 *)*((_QWORD *)a1 + 1);
    v5 = *(_QWORD *)(i + 8) - (_QWORD)v4;
    do
    {
      v6 = *(unsigned __int16 *)((char *)v4 + v5);
      v7 = *v4 - v6;
      if ( v7 )
        break;
      ++v4;
    }
    while ( v6 );
    if ( !v7 )
      break;
  }
  v8 = 1;
  if ( *a1 == 1 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAppend(L" <%s, %d, TPS_Error>\n", *(_QWORD *)(i + 8), a1[1]);
    v2 = RemoveProviderFromList((struct TimeProvider *)i, 1, 0);
    if ( v2 < 0 && (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAdd(L"Couldn't remove provider from list: %s\n", *(_QWORD *)(i + 8));
LABEL_52:
    _set_se_translator(v17);
    if ( v2 >= 0 )
      v2 = 0;
    goto LABEL_54;
  }
  if ( *a1 )
  {
    if ( (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAppend(L"bad provider status code, %d\n", *a1);
    v2 = -2147024809;
  }
  else
  {
    v9 = a1[1];
    if ( !v9 || *(_DWORD *)(i + 64) <= v9 )
    {
      if ( (unsigned __int8)FileLogAllowEntry(64) )
        FileLogAppend(L"<%s, %d, TPS_Running>\n", *(_QWORD *)(i + 8), a1[1]);
      *(_DWORD *)(i + 64) = a1[1];
      if ( dword_1800A3810 == 3 || (v10 = a1[1]) != 0 && dword_1800A3814 >= v10 )
      {
        if ( (unsigned __int8)FileLogAllowEntry(64) )
          FileLogAdd(
            L"Systerm stratum is not updated due to new stratum (%d) is superior to the system stratum stratum (%d).\n",
            a1[1],
            dword_1800A3814);
        v8 = 0;
      }
      else
      {
        for ( j = *(_QWORD *)qword_1800A42F0; j; j = *(_QWORD *)(j + 24) )
        {
          if ( *(_DWORD *)(j + 64) )
          {
            v12 = a1[1];
            if ( !v12 || v12 > *(_DWORD *)(j + 64) )
            {
              if ( (unsigned __int8)FileLogAllowEntry(64) )
                FileLogAdd(
                  L"Systerm stratum is not updated due to new stratum (%d) is NOT superior to this provider's stratum (%d).\n",
                  a1[1],
                  *(unsigned int *)(j + 64));
              v8 = 0;
            }
          }
        }
      }
      v13 = FileLogAllowEntry(64);
      if ( v8 )
      {
        if ( v13 )
          FileLogAdd(L"***System stratum updated***, %d --> %d\n", dword_1800A3814, a1[1]);
        dword_1800A3814 = a1[1];
        if ( !dword_1800A3814 )
          dword_1800A3810 = 3;
      }
      else if ( v13 )
      {
        FileLogAdd(L"System stratum not updated: %d\n", dword_1800A3814);
      }
      goto LABEL_52;
    }
    if ( (unsigned __int8)FileLogAllowEntry(64) )
      FileLogAppend(L"stratum too low (best provider stratum == %d).\n", *(unsigned int *)(i + 64));
    v2 = -2147024809;
  }
LABEL_54:
  if ( a1 )
  {
    v14 = (int *)*((_QWORD *)a1 + 4);
    if ( v14 )
      *v14 = v2;
    if ( *((_QWORD *)a1 + 5) )
      **((_DWORD **)a1 + 5) = dword_1800A3814;
    v15 = (void *)*((_QWORD *)a1 + 2);
    if ( v15 )
      SetEvent(v15);
    (*((void (__fastcall **)(unsigned int *))a1 + 3))(a1);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003891c  mov     [rsp+arg_10], rbx
0x180038921  push    rsi
0x180038922  push    rdi
0x180038923  push    r12
0x180038925  push    r14
0x180038927  push    r15
0x180038929  sub     rsp, 60h
0x18003892d  mov     rsi, rcx
0x180038930  mov     [rsp+88h+arg_0], rcx
0x180038938  lea     rcx, ?SeTransFunc@@YAXIPEAU_EXCEPTION_POINTERS@@@Z; SeTransFunc(uint,_EXCEPTION_POINTERS *)
0x18003893f  call    cs:__imp__set_se_translator
0x180038946  nop     dword ptr [rax+rax+00h]
0x18003894b  mov     [rsp+88h+arg_8], rax
0x180038953  xor     ebx, ebx
0x180038955  mov     edi, ebx
0x180038957  lea     r12d, [rbx+40h]
0x18003895b  mov     ecx, r12d
0x18003895e  call    FileLogAllowEntry
0x180038963  test    al, al
0x180038965  jz      short loc_180038973
0x180038967  lea     rcx, aW32tmservicema_4; "W32TmServiceMain: SetProviderStatusWork"...
0x18003896e  call    FileLogAdd
0x180038973  mov     rax, cs:qword_1800A42F0
0x18003897a  mov     r14, [rax]
0x18003897d  test    r14, r14
0x180038980  jz      loc_180038B9F
0x180038986  mov     rax, [rsi+8]
0x18003898a  mov     rdx, [r14+8]
0x18003898e  sub     rdx, rax
0x180038991  movzx   ecx, word ptr [rax]
0x180038994  movzx   r8d, word ptr [rax+rdx]
0x180038999  sub     ecx, r8d
0x18003899c  jnz     short loc_1800389A7
0x18003899e  add     rax, 2
0x1800389a2  test    r8d, r8d
0x1800389a5  jnz     short loc_180038991
0x1800389a7  test    ecx, ecx
0x1800389a9  jz      short loc_1800389B1
0x1800389ab  mov     r14, [r14+18h]
0x1800389af  jmp     short loc_18003897D
0x1800389b1  mov     r15d, 1
0x1800389b7  cmp     [rsi], r15d
0x1800389ba  jnz     short loc_180038A1D
0x1800389bc  mov     ecx, r12d
0x1800389bf  call    FileLogAllowEntry
0x1800389c4  test    al, al
0x1800389c6  jz      short loc_1800389DC
0x1800389c8  mov     r8d, [rsi+4]
0x1800389cc  mov     rdx, [r14+8]
0x1800389d0  lea     rcx, aSDTpsError; " <%s, %d, TPS_Error>\n"
0x1800389d7  call    FileLogAppend
0x1800389dc  xor     r8d, r8d; bool *
0x1800389df  mov     dl, r15b; bool
0x1800389e2  mov     rcx, r14; struct TimeProvider *
0x1800389e5  call    ?RemoveProviderFromList@@YAJPEAUTimeProvider@@_NPEA_N@Z; RemoveProviderFromList(TimeProvider *,bool,bool *)
0x1800389ea  mov     edi, eax
0x1800389ec  mov     [rsp+88h+var_64], eax
0x1800389f0  test    eax, eax
0x1800389f2  jns     loc_180038B78
0x1800389f8  mov     ecx, r12d
0x1800389fb  call    FileLogAllowEntry
0x180038a00  test    al, al
0x180038a02  jz      loc_180038B78
0x180038a08  mov     rdx, [r14+8]
0x180038a0c  lea     rcx, aCouldnTRemoveP; "Couldn't remove provider from list: %s"...
0x180038a13  call    FileLogAdd
0x180038a18  jmp     loc_180038B78
0x180038a1d  cmp     [rsi], ebx
0x180038a1f  jnz     loc_180038B7A
0x180038a25  mov     eax, [rsi+4]
0x180038a28  test    eax, eax
0x180038a2a  jz      short loc_180038A5C
0x180038a2c  cmp     [r14+40h], eax
0x180038a30  jbe     short loc_180038A5C
0x180038a32  mov     ecx, r12d
0x180038a35  call    FileLogAllowEntry
0x180038a3a  test    al, al
0x180038a3c  jz      short loc_180038A4E
0x180038a3e  mov     edx, [r14+40h]
0x180038a42  lea     rcx, aStratumTooLowB; "stratum too low (best provider stratum "...
0x180038a49  call    FileLogAppend
0x180038a4e  mov     edi, 80070057h
0x180038a53  mov     [rsp+88h+var_64], edi
0x180038a57  jmp     loc_180038BED
0x180038a5c  mov     ecx, r12d
0x180038a5f  call    FileLogAllowEntry
0x180038a64  test    al, al
0x180038a66  jz      short loc_180038A7C
0x180038a68  mov     r8d, [rsi+4]
0x180038a6c  mov     rdx, [r14+8]
0x180038a70  lea     rcx, aSDTpsRunning; "<%s, %d, TPS_Running>\n"
0x180038a77  call    FileLogAppend
0x180038a7c  mov     eax, [rsi+4]
0x180038a7f  mov     [r14+40h], eax
0x180038a83  mov     eax, cs:dword_1800A3810
0x180038a89  cmp     eax, 3
0x180038a8c  jz      short loc_180038AF2
0x180038a8e  mov     ecx, [rsi+4]
0x180038a91  test    ecx, ecx
0x180038a93  jz      short loc_180038A9F
0x180038a95  mov     eax, cs:dword_1800A3814
0x180038a9b  cmp     eax, ecx
0x180038a9d  jnb     short loc_180038AF2
0x180038a9f  mov     [rsp+88h+var_68], r15b
0x180038aa4  mov     rax, cs:qword_1800A42F0
0x180038aab  mov     r14, [rax]
0x180038aae  test    r14, r14
0x180038ab1  jz      short loc_180038B1B
0x180038ab3  cmp     [r14+40h], ebx
0x180038ab7  jz      short loc_180038AEC
0x180038ab9  mov     eax, [rsi+4]
0x180038abc  test    eax, eax
0x180038abe  jz      short loc_180038AC6
0x180038ac0  cmp     eax, [r14+40h]
0x180038ac4  jbe     short loc_180038AEC
0x180038ac6  mov     ecx, r12d
0x180038ac9  call    FileLogAllowEntry
0x180038ace  test    al, al
0x180038ad0  jz      short loc_180038AE5
0x180038ad2  mov     r8d, [r14+40h]
0x180038ad6  mov     edx, [rsi+4]
0x180038ad9  lea     rcx, aSystermStratum; "Systerm stratum is not updated due to n"...
0x180038ae0  call    FileLogAdd
0x180038ae5  mov     r15b, bl
0x180038ae8  mov     [rsp+88h+var_68], bl
0x180038aec  mov     r14, [r14+18h]
0x180038af0  jmp     short loc_180038AAE
0x180038af2  mov     ecx, r12d
0x180038af5  call    FileLogAllowEntry
0x180038afa  test    al, al
0x180038afc  jz      short loc_180038B14
0x180038afe  mov     edx, [rsi+4]
0x180038b01  mov     r8d, cs:dword_1800A3814
0x180038b08  lea     rcx, aSystermStratum_0; "Systerm stratum is not updated due to n"...
0x180038b0f  call    FileLogAdd
0x180038b14  mov     r15b, bl
0x180038b17  mov     [rsp+88h+var_68], bl
0x180038b1b  mov     ecx, r12d
0x180038b1e  call    FileLogAllowEntry
0x180038b23  test    r15b, r15b
0x180038b26  jz      short loc_180038B61
0x180038b28  test    al, al
0x180038b2a  jz      short loc_180038B42
0x180038b2c  mov     r8d, [rsi+4]
0x180038b30  mov     edx, cs:dword_1800A3814
0x180038b36  lea     rcx, aSystemStratumU; "***System stratum updated***, %d --> %d"...
0x180038b3d  call    FileLogAdd
0x180038b42  mov     eax, [rsi+4]
0x180038b45  mov     cs:dword_1800A3814, eax
0x180038b4b  mov     eax, cs:dword_1800A3814
0x180038b51  test    eax, eax
0x180038b53  jnz     short loc_180038B78
0x180038b55  mov     cs:dword_1800A3810, 3
0x180038b5f  jmp     short loc_180038B78
0x180038b61  test    al, al
0x180038b63  jz      short loc_180038B78
0x180038b65  mov     edx, cs:dword_1800A3814
0x180038b6b  lea     rcx, aSystemStratumN; "System stratum not updated: %d\n"
0x180038b72  call    FileLogAdd
0x180038b77  nop
0x180038b78  jmp     short loc_180038BD4
0x180038b7a  mov     ecx, r12d
0x180038b7d  call    FileLogAllowEntry
0x180038b82  test    al, al
0x180038b84  jz      short loc_180038B94
0x180038b86  mov     edx, [rsi]
0x180038b88  lea     rcx, aBadProviderSta; "bad provider status code, %d\n"
0x180038b8f  call    FileLogAppend
0x180038b94  mov     edi, 80070057h
0x180038b99  mov     [rsp+88h+var_64], edi
0x180038b9d  jmp     short loc_180038BED
0x180038b9f  mov     ecx, r12d
0x180038ba2  call    FileLogAllowEntry
0x180038ba7  test    al, al
0x180038ba9  jz      short loc_180038BB7
0x180038bab  lea     rcx, aProviderNotFou; "provider not found.\n"
0x180038bb2  call    FileLogAppend
0x180038bb7  mov     edi, 80070057h
0x180038bbc  mov     [rsp+88h+var_64], edi
0x180038bc0  jmp     short loc_180038BED
0x180038bc2  jmp     short loc_180038BC6
0x180038bc4  jmp     short $+2
0x180038bc6  xor     ebx, ebx
0x180038bc8  mov     edi, [rsp+88h+var_64]
0x180038bcc  mov     rsi, [rsp+88h+arg_0]
0x180038bd4  mov     rcx, [rsp+88h+arg_8]
0x180038bdc  call    cs:__imp__set_se_translator
0x180038be3  nop     dword ptr [rax+rax+00h]
0x180038be8  test    edi, edi
0x180038bea  cmovns  edi, ebx
0x180038bed  test    rsi, rsi
0x180038bf0  jz      short loc_180038C30
0x180038bf2  mov     rax, [rsi+20h]
0x180038bf6  test    rax, rax
0x180038bf9  jz      short loc_180038BFD
0x180038bfb  mov     [rax], edi
0x180038bfd  cmp     [rsi+28h], rbx
0x180038c01  jz      short loc_180038C0F
0x180038c03  mov     rdx, [rsi+28h]
0x180038c07  mov     eax, cs:dword_1800A3814
0x180038c0d  mov     [rdx], eax
0x180038c0f  mov     rcx, [rsi+10h]; hEvent
0x180038c13  test    rcx, rcx
0x180038c16  jz      short loc_180038C24
0x180038c18  call    cs:__imp_SetEvent
0x180038c1f  nop     dword ptr [rax+rax+00h]
0x180038c24  mov     rcx, rsi
0x180038c27  mov     rax, [rsi+18h]
0x180038c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c30  mov     eax, edi
0x180038c32  mov     rbx, [rsp+88h+arg_10]
0x180038c3a  add     rsp, 60h
0x180038c3e  pop     r15
0x180038c40  pop     r14
0x180038c42  pop     r12
0x180038c44  pop     rdi
0x180038c45  pop     rsi
0x180038c46  retn
```
