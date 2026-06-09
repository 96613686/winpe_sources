# SclpStateValidateAndRetrieveChangedKeys

- ea: `0x18000548c`
- end: `0x18000592f`
- name: `SclpStateValidateAndRetrieveChangedKeys`
- size: `1187`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _QWORD *, void *, PCWSTR SourceString, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004844`

## callees

- `0x1800025ec`
- `0x180004f5c`
- `0x18000548c`
- `0x180007ac4`
- `0x18000923c`
- `0x180009668`
- `0x18000a524`
- `0x18000a75c`
- `0x18000aaac`
- `0x18000ab04`
- `0x1800153c8`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180005686`
- `ntdll!RtlAllocateHeap` at `0x1800056b4`
- `ntdll!RtlAllocateHeap` at `0x18000575b`
- `ntdll!RtlAllocateHeap` at `0x180005686`
- `ntdll!RtlAllocateHeap` at `0x1800056b4`
- `ntdll!RtlAllocateHeap` at `0x18000575b`
- `ntdll!RtlInitUnicodeString` at `0x1800054e9`
- `ntdll!RtlInitUnicodeString` at `0x1800056d2`
- `ntdll!RtlInitUnicodeString` at `0x1800054e9`
- `ntdll!RtlInitUnicodeString` at `0x1800056d2`
- `ntdll!NtClose` at `0x18000589e`
- `ntdll!NtClose` at `0x1800058ad`
- `ntdll!NtClose` at `0x18000589e`
- `ntdll!NtClose` at `0x1800058ad`
- `ntdll!RtlFreeHeap` at `0x180005878`
- `ntdll!RtlFreeHeap` at `0x1800058d2`
- `ntdll!RtlFreeHeap` at `0x1800058ef`
- `ntdll!RtlFreeHeap` at `0x18000590c`
- `ntdll!RtlFreeHeap` at `0x180005878`
- `ntdll!RtlFreeHeap` at `0x1800058d2`
- `ntdll!RtlFreeHeap` at `0x1800058ef`
- `ntdll!RtlFreeHeap` at `0x18000590c`

## string_xrefs

- `0x18000551a`: `System32\config`
- `0x1800057d8`: `(%lx): Failure during enumeration of values.`

## pseudocode

```c
__int64 __fastcall SclpStateValidateAndRetrieveChangedKeys(
        __int64 a1,
        const wchar_t *a2,
        _QWORD *a3,
        void *a4,
        PCWSTR SourceString,
        _QWORD *a6)
{
  _QWORD *v9; // r12
  WCHAR *v10; // rdi
  void *v11; // rsi
  int v12; // ebx
  wchar_t *v13; // rax
  wchar_t *v14; // r13
  int v15; // eax
  int Value; // eax
  unsigned int *v17; // rcx
  char v18; // r14
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  void *v22; // rdi
  int i; // eax
  int v24; // eax
  _QWORD *v25; // rax
  _QWORD *v26; // r15
  __int64 v27; // rcx
  __int64 v28; // rcx
  const wchar_t *v29; // rax
  ULONG v31; // [rsp+28h] [rbp-59h]
  unsigned int *Heap; // [rsp+48h] [rbp-39h] BYREF
  int v33; // [rsp+50h] [rbp-31h]
  __int64 v34; // [rsp+58h] [rbp-29h] BYREF
  WCHAR *v35; // [rsp+60h] [rbp-21h] BYREF
  HANDLE KeyHandle; // [rsp+68h] [rbp-19h] BYREF
  int v37; // [rsp+70h] [rbp-11h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp-9h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-1h] BYREF

  v35 = 0;
  KeyHandle = 0;
  Handle = 0;
  Heap = 0;
  v34 = 0;
  v9 = 0;
  DestinationString = 0;
  v10 = 0;
  v11 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  v12 = SclOpenKey(a4, &DestinationString, 0x20019u, 0, &KeyHandle);
  if ( v12 < 0 )
  {
    v14 = 0;
  }
  else
  {
    v13 = BuildPathMulti(3u, a2, L"System32\\config", SourceString);
    v14 = v13;
    if ( v13 )
    {
      v15 = SclDosPathToNtPath((__int64)v13, &v35);
      v10 = v35;
      v12 = v15;
      if ( v15 >= 0 )
      {
        v12 = SclpFileGetLastWriteTime(v35, &Heap);
        if ( v12 >= 0 )
        {
          Value = SclRegGetValue(KeyHandle, v31);
          v11 = (void *)v34;
          v12 = Value;
          if ( Value >= 0 )
          {
            if ( *(_DWORD *)(v34 + 4) == 11 )
            {
              if ( *(_DWORD *)(v34 + 8) == 8 )
              {
                v17 = *(unsigned int **)(v34 + 12);
                if ( v17 != Heap )
                {
                  v18 = 0;
                  if ( a3 )
                  {
                    if ( *a3 <= (__int64)v17 || (__int64)Heap <= *a3 )
                    {
                      v20 = a1 + 1152;
                      if ( !a1 )
                        v20 = 0;
                      SclLogGenericMessage(
                        v20,
                        1,
                        (int)SclEvent_Generic_Info,
                        2432,
                        (__int64)"SclpStateValidateAndRetrieveChangedKeys",
                        "Hive [%ws] changed before boot; will skip the changed keys list.",
                        SourceString);
                    }
                    else
                    {
                      v19 = a1 + 1152;
                      v18 = 1;
                      if ( !a1 )
                        v19 = 0;
                      SclLogGenericMessage(
                        v19,
                        1,
                        (int)SclEvent_Generic_Info,
                        2423,
                        (__int64)"SclpStateValidateAndRetrieveChangedKeys",
                        "Hive [%ws] changed only after boot; will get the changed keys list.",
                        SourceString);
                    }
                  }
                  else
                  {
                    v21 = a1 + 1152;
                    if ( !a1 )
                      v21 = 0;
                    SclLogGenericMessage(
                      v21,
                      1,
                      (int)SclEvent_Generic_Info,
                      2440,
                      (__int64)"SclpStateValidateAndRetrieveChangedKeys",
                      "Change tags mismatch for hive [%ws]; will skip the changed keys list.",
                      SourceString);
                  }
                  if ( !v18 )
                    goto LABEL_50;
                }
                LODWORD(v34) = 4120;
                Heap = (unsigned int *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x1018u);
                v22 = Heap;
                if ( Heap && (v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u)) != 0 )
                {
                  RtlInitUnicodeString(&DestinationString, L"ChangedKeys");
                  v12 = SclOpenKey(KeyHandle, &DestinationString, 0x20019u, 0, &Handle);
                }
                else
                {
                  v12 = -1073741801;
                }
                for ( i = 0; ; i = v33 + 1 )
                {
                  v33 = i;
                  if ( v12 < 0 )
                    break;
                  v37 = 0;
                  v24 = SclRegEnumerateValueKey((_DWORD)Handle, i, 1, (unsigned int)&Heap, (__int64)&v34, (__int64)&v37);
                  v12 = v24;
                  if ( v24 == -2147483622 )
                  {
                    v12 = 0;
                    v28 = a1 + 1152;
                    if ( !a1 )
                      v28 = 0;
                    v29 = L"No";
                    if ( *v9 )
                      v29 = L"Retrieved";
                    SclLogGenericMessage(
                      v28,
                      1,
                      (int)SclEvent_Generic_Info,
                      2545,
                      (__int64)"SclpStateValidateAndRetrieveChangedKeys",
                      "%ws changes to be made to hive [%ws]",
                      v29,
                      SourceString);
                    goto LABEL_46;
                  }
                  if ( v24 < 0 )
                  {
                    v27 = a1 + 1152;
                    if ( !a1 )
                      v27 = 0;
                    SclLogGenericMessage(
                      v27,
                      3,
                      (int)SclEvent_Generic_Error,
                      2510,
                      (__int64)"SclpStateValidateAndRetrieveChangedKeys",
                      "(%lx): Failure during enumeration of values.",
                      v24);
LABEL_46:
                    v22 = Heap;
                    break;
                  }
                  v25 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x10u);
                  v22 = Heap;
                  v26 = v25;
                  if ( v25 )
                  {
                    v12 = SclCloneString((_WORD *)Heap + 10, (unsigned __int64)Heap[4] >> 1, v25 + 1, 0);
                    if ( v12 >= 0 )
                    {
                      *v26 = *v9;
                      *v9 = v26;
                      v26 = 0;
                    }
                  }
                  else
                  {
                    v12 = -1073741801;
                  }
                  SclFreeChangedKeyItem(v26);
                }
                if ( v22 )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v22);
                v10 = v35;
                if ( v12 >= 0 )
                {
LABEL_50:
                  *a6 = v9;
                  v9 = 0;
                }
              }
              else
              {
                v12 = -1073741820;
              }
            }
            else
            {
              v12 = -1073741788;
            }
          }
        }
      }
    }
    else
    {
      v12 = -1073741801;
    }
  }
  if ( Handle )
    NtClose(Handle);
  if ( KeyHandle )
    NtClose(KeyHandle);
  SclFreeChangedKeys(v9);
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v14 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v14);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000548c  mov     rax, rsp
0x18000548f  mov     [rax+10h], rbx
0x180005493  mov     [rax+18h], r8
0x180005497  mov     [rax+8], rcx
0x18000549b  push    rbp
0x18000549c  push    rsi
0x18000549d  push    rdi
0x18000549e  push    r12
0x1800054a0  push    r13
0x1800054a2  push    r14
0x1800054a4  push    r15
0x1800054a6  lea     rbp, [rax-4Fh]
0x1800054aa  sub     rsp, 90h
0x1800054b1  mov     r13, [rbp+47h+SourceString]
0x1800054b5  xor     eax, eax
0x1800054b7  mov     r14, rdx
0x1800054ba  mov     [rbp+47h+var_68], rax
0x1800054be  mov     r15, rcx
0x1800054c1  mov     [rbp+47h+KeyHandle], rax
0x1800054c5  xorps   xmm0, xmm0
0x1800054c8  mov     [rbp+47h+Handle], rax
0x1800054cc  mov     rdx, r13; SourceString
0x1800054cf  mov     [rbp+47h+var_80], rax
0x1800054d3  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1800054d7  mov     [rbp+47h+var_70], rax
0x1800054db  mov     rbx, r9
0x1800054de  mov     r12d, eax
0x1800054e1  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x1800054e5  mov     edi, eax
0x1800054e7  mov     esi, eax
0x1800054e9  call    cs:__imp_RtlInitUnicodeString
0x1800054ef  lea     rax, [rbp+47h+KeyHandle]
0x1800054f3  xor     r9d, r9d
0x1800054f6  mov     r8d, 20019h
0x1800054fc  mov     qword ptr [rsp+0C0h+var_A0], rax; ULONG
0x180005501  lea     rdx, [rbp+47h+DestinationString]
0x180005505  mov     rcx, rbx
0x180005508  call    SclOpenKey
0x18000550d  mov     ebx, eax
0x18000550f  test    eax, eax
0x180005511  js      loc_180005892
0x180005517  mov     r9, r13
0x18000551a  lea     r8, aSystem32Config; "System32\\config"
0x180005521  mov     rdx, r14
0x180005524  lea     ecx, [rsi+3]
0x180005527  call    BuildPathMulti
0x18000552c  mov     r13, rax
0x18000552f  test    rax, rax
0x180005532  jnz     short loc_18000553E
0x180005534  mov     ebx, 0C0000017h
0x180005539  jmp     loc_180005895
0x18000553e  lea     rdx, [rbp+47h+var_68]
0x180005542  mov     rcx, rax
0x180005545  call    SclDosPathToNtPath
0x18000554a  mov     rdi, [rbp+47h+var_68]
0x18000554e  mov     ebx, eax
0x180005550  test    eax, eax
0x180005552  js      loc_180005895
0x180005558  lea     rdx, [rbp+47h+var_80]
0x18000555c  mov     rcx, rdi
0x18000555f  call    SclpFileGetLastWriteTime
0x180005564  mov     ebx, eax
0x180005566  test    eax, eax
0x180005568  js      loc_180005895
0x18000556e  mov     rcx, [rbp+47h+KeyHandle]; KeyHandle
0x180005572  lea     r9, [rbp+47h+var_70]
0x180005576  xor     r8d, r8d
0x180005579  lea     rdx, aChangetag; "ChangeTag"
0x180005580  call    SclRegGetValue
0x180005585  mov     rsi, [rbp+47h+var_70]
0x180005589  mov     ebx, eax
0x18000558b  test    eax, eax
0x18000558d  js      loc_180005895
0x180005593  cmp     dword ptr [rsi+4], 0Bh
0x180005597  jz      short loc_1800055A3
0x180005599  mov     ebx, 0C0000024h
0x18000559e  jmp     loc_180005895
0x1800055a3  cmp     dword ptr [rsi+8], 8
0x1800055a7  jz      short loc_1800055B3
0x1800055a9  mov     ebx, 0C0000004h
0x1800055ae  jmp     loc_180005895
0x1800055b3  mov     rcx, [rsi+0Ch]
0x1800055b7  lea     r10, aSclpstatevalid; "SclpStateValidateAndRetrieveChangedKeys"
0x1800055be  mov     edx, 1
0x1800055c3  cmp     rcx, [rbp+47h+var_80]
0x1800055c7  jz      loc_18000566D
0x1800055cd  mov     rax, [rbp+47h+arg_10]
0x1800055d1  xor     r14b, r14b
0x1800055d4  test    rax, rax
0x1800055d7  jz      short loc_180005628
0x1800055d9  mov     rax, [rax]
0x1800055dc  cmp     rax, rcx
0x1800055df  jle     short loc_180005609
0x1800055e1  cmp     [rbp+47h+var_80], rax
0x1800055e5  jle     short loc_180005609
0x1800055e7  xor     eax, eax
0x1800055e9  lea     rcx, [r15+480h]
0x1800055f0  test    r15, r15
0x1800055f3  mov     r14b, dl
0x1800055f6  mov     r9d, 977h
0x1800055fc  cmovz   rcx, rax
0x180005600  lea     rax, aHiveWsChangedO; "Hive [%ws] changed only after boot; wil"...
0x180005607  jmp     short loc_180005645
0x180005609  xor     eax, eax
0x18000560b  lea     rcx, [r15+480h]
0x180005612  test    r15, r15
0x180005615  mov     r9d, 980h
0x18000561b  cmovz   rcx, rax
0x18000561f  lea     rax, aHiveWsChangedB; "Hive [%ws] changed before boot; will sk"...
0x180005626  jmp     short loc_180005645
0x180005628  xor     eax, eax
0x18000562a  lea     rcx, [r15+480h]
0x180005631  test    r15, r15
0x180005634  mov     r9d, 988h
0x18000563a  cmovz   rcx, rax
0x18000563e  lea     rax, aChangeTagsMism; "Change tags mismatch for hive [%ws]; wi"...
0x180005645  mov     r11, [rbp+47h+SourceString]
0x180005649  lea     r8, SclEvent_Generic_Info
0x180005650  mov     [rsp+0C0h+var_90], r11
0x180005655  mov     [rsp+0C0h+var_98], rax
0x18000565a  mov     qword ptr [rsp+0C0h+var_A0], r10
0x18000565f  call    SclLogGenericMessage
0x180005664  test    r14b, r14b
0x180005667  jz      loc_180005886
0x18000566d  mov     rcx, gs:60h
0x180005676  mov     r8d, 1018h; Size
0x18000567c  xor     edx, edx; Flags
0x18000567e  mov     dword ptr [rbp+47h+var_70], r8d
0x180005682  mov     rcx, [rcx+30h]; HeapHandle
0x180005686  call    cs:__imp_RtlAllocateHeap
0x18000568c  mov     [rbp+47h+var_80], rax
0x180005690  mov     rdi, rax
0x180005693  mov     r14d, 0C0000017h
0x180005699  test    rax, rax
0x18000569c  jz      short loc_1800056C2
0x18000569e  mov     rcx, gs:60h
0x1800056a7  mov     edx, 8; Flags
0x1800056ac  mov     rcx, [rcx+30h]; HeapHandle
0x1800056b0  lea     r8d, [rdx+8]; Size
0x1800056b4  call    cs:__imp_RtlAllocateHeap
0x1800056ba  mov     r12, rax
0x1800056bd  test    rax, rax
0x1800056c0  jnz     short loc_1800056C7
0x1800056c2  mov     ebx, r14d
0x1800056c5  jmp     short loc_1800056F9
0x1800056c7  lea     rdx, SourceString; "ChangedKeys"
0x1800056ce  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1800056d2  call    cs:__imp_RtlInitUnicodeString
0x1800056d8  mov     rcx, [rbp+47h+KeyHandle]
0x1800056dc  lea     rax, [rbp+47h+Handle]
0x1800056e0  xor     r9d, r9d
0x1800056e3  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800056e8  mov     r8d, 20019h
0x1800056ee  lea     rdx, [rbp+47h+DestinationString]
0x1800056f2  call    SclOpenKey
0x1800056f7  mov     ebx, eax
0x1800056f9  xor     eax, eax
0x1800056fb  mov     [rbp+47h+var_78], eax
0x1800056fe  test    ebx, ebx
0x180005700  js      loc_180005861
0x180005706  lea     rcx, [rbp+47h+var_58]
0x18000570a  mov     [rbp+47h+var_58], 0
0x180005711  mov     [rsp+0C0h+var_98], rcx
0x180005716  lea     r9, [rbp+47h+var_80]
0x18000571a  lea     rcx, [rbp+47h+var_70]
0x18000571e  mov     edi, 1
0x180005723  mov     qword ptr [rsp+0C0h+var_A0], rcx
0x180005728  mov     r8d, edi
0x18000572b  mov     rcx, [rbp+47h+Handle]
0x18000572f  mov     edx, eax
0x180005731  call    SclRegEnumerateValueKey
0x180005736  mov     ebx, eax
0x180005738  cmp     eax, 8000001Ah
0x18000573d  jz      loc_1800057F7
0x180005743  test    eax, eax
0x180005745  js      short loc_1800057AE
0x180005747  mov     rcx, gs:60h
0x180005750  lea     edx, [rdi+7]; Flags
0x180005753  lea     r8d, [rdi+0Fh]; Size
0x180005757  mov     rcx, [rcx+30h]; HeapHandle
0x18000575b  call    cs:__imp_RtlAllocateHeap
0x180005761  mov     rdi, [rbp+47h+var_80]
0x180005765  mov     r15, rax
0x180005768  test    rax, rax
0x18000576b  jnz     short loc_180005772
0x18000576d  mov     ebx, r14d
0x180005770  jmp     short loc_18000579C
0x180005772  mov     edx, [rdi+10h]
0x180005775  lea     r8, [rax+8]
0x180005779  shr     rdx, 1
0x18000577c  lea     rcx, [rdi+14h]
0x180005780  xor     r9d, r9d
0x180005783  call    SclCloneString
0x180005788  mov     ebx, eax
0x18000578a  test    eax, eax
0x18000578c  js      short loc_18000579C
0x18000578e  mov     rax, [r12]
0x180005792  mov     [r15], rax
0x180005795  mov     [r12], r15
0x180005799  xor     r15d, r15d
0x18000579c  mov     rcx, r15; P
0x18000579f  call    SclFreeChangedKeyItem
0x1800057a4  mov     eax, [rbp+47h+var_78]
0x1800057a7  inc     eax
0x1800057a9  jmp     loc_1800056FB
0x1800057ae  mov     r8, [rbp+47h+arg_0]
0x1800057b2  xor     eax, eax
0x1800057b4  test    r8, r8
0x1800057b7  mov     dword ptr [rsp+0C0h+var_90], ebx
0x1800057bb  mov     r9d, 9CEh
0x1800057c1  mov     edx, 3
0x1800057c6  lea     rcx, [r8+480h]
0x1800057cd  cmovz   rcx, rax
0x1800057d1  lea     r8, SclEvent_Generic_Error
0x1800057d8  lea     rax, aLxFailureDurin_0; "(%lx): Failure during enumeration of va"...
0x1800057df  mov     [rsp+0C0h+var_98], rax
0x1800057e4  lea     rax, aSclpstatevalid; "SclpStateValidateAndRetrieveChangedKeys"
0x1800057eb  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1800057f0  call    SclLogGenericMessage
0x1800057f5  jmp     short loc_18000585D
0x1800057f7  mov     r8, [rbp+47h+arg_0]
0x1800057fb  lea     r9, aRetrieved; "Retrieved"
0x180005802  mov     rdx, [rbp+47h+SourceString]
0x180005806  xor     eax, eax
0x180005808  mov     [rsp+38h], rdx
0x18000580d  xor     ebx, ebx
0x18000580f  test    r8, r8
0x180005812  mov     edx, edi
0x180005814  lea     rcx, [r8+480h]
0x18000581b  cmovz   rcx, rax
0x18000581f  lea     r8, SclEvent_Generic_Info
0x180005826  cmp     [r12], rbx
0x18000582a  lea     rax, aNo; "No"
0x180005831  cmovnz  rax, r9
0x180005835  mov     r9d, 9F1h
0x18000583b  mov     [rsp+0C0h+var_90], rax
0x180005840  lea     rax, aWsChangesToBeM; "%ws changes to be made to hive [%ws]"
0x180005847  mov     [rsp+0C0h+var_98], rax
0x18000584c  lea     rax, aSclpstatevalid; "SclpStateValidateAndRetrieveChangedKeys"
0x180005853  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180005858  call    SclLogGenericMessage
0x18000585d  mov     rdi, [rbp+47h+var_80]
0x180005861  test    rdi, rdi
0x180005864  jz      short loc_18000587E
0x180005866  mov     rcx, gs:60h
0x18000586f  mov     r8, rdi; P
0x180005872  xor     edx, edx; Flags
0x180005874  mov     rcx, [rcx+30h]; HeapHandle
0x180005878  call    cs:__imp_RtlFreeHeap
0x18000587e  mov     rdi, [rbp+47h+var_68]
0x180005882  test    ebx, ebx
0x180005884  js      short loc_180005895
0x180005886  mov     rax, [rbp+47h+arg_28]
0x18000588a  mov     [rax], r12
0x18000588d  xor     r12d, r12d
0x180005890  jmp     short loc_180005895
0x180005892  xor     r13d, r13d
0x180005895  mov     rcx, [rbp+47h+Handle]; Handle
0x180005899  test    rcx, rcx
0x18000589c  jz      short loc_1800058A4
0x18000589e  call    cs:__imp_NtClose
0x1800058a4  mov     rcx, [rbp+47h+KeyHandle]; Handle
0x1800058a8  test    rcx, rcx
0x1800058ab  jz      short loc_1800058B3
0x1800058ad  call    cs:__imp_NtClose
0x1800058b3  mov     rcx, r12; P
0x1800058b6  call    SclFreeChangedKeys
0x1800058bb  test    rsi, rsi
0x1800058be  jz      short loc_1800058D8
0x1800058c0  mov     rcx, gs:60h
0x1800058c9  mov     r8, rsi; P
0x1800058cc  xor     edx, edx; Flags
0x1800058ce  mov     rcx, [rcx+30h]; HeapHandle
0x1800058d2  call    cs:__imp_RtlFreeHeap
0x1800058d8  test    rdi, rdi
0x1800058db  jz      short loc_1800058F5
0x1800058dd  mov     rcx, gs:60h
0x1800058e6  mov     r8, rdi; P
0x1800058e9  xor     edx, edx; Flags
0x1800058eb  mov     rcx, [rcx+30h]; HeapHandle
0x1800058ef  call    cs:__imp_RtlFreeHeap
0x1800058f5  test    r13, r13
0x1800058f8  jz      short loc_180005912
0x1800058fa  mov     rcx, gs:60h
0x180005903  mov     r8, r13; P
0x180005906  xor     edx, edx; Flags
0x180005908  mov     rcx, [rcx+30h]; HeapHandle
0x18000590c  call    cs:__imp_RtlFreeHeap
0x180005912  mov     eax, ebx
0x180005914  mov     rbx, [rsp+0C0h+arg_8]
0x18000591c  add     rsp, 90h
0x180005923  pop     r15
0x180005925  pop     r14
0x180005927  pop     r13
0x180005929  pop     r12
0x18000592b  pop     rdi
0x18000592c  pop     rsi
0x18000592d  pop     rbp
0x18000592e  retn
```
