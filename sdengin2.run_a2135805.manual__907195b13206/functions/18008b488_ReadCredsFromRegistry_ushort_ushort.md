# ReadCredsFromRegistry(ushort * *,ushort * *)

- ea: `0x18008b488`
- end: `0x18008b76d`
- name: `?ReadCredsFromRegistry@@YAJPEAPEAG0@Z`
- size: `741`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002935c`
- `0x180040a54`
- `0x18008ccf0`

## callees

- `0x180072e08`
- `0x180072f14`
- `0x18008b238`
- `0x18008b488`
- `0x18008c1cc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b723`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b73c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b723`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008b73c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b544`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b591`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b544`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b591`
- `ole32!CoTaskMemFree` at `0x18008b6e3`
- `ole32!CoTaskMemFree` at `0x18008b70e`
- `ole32!CoTaskMemFree` at `0x18008b6e3`
- `ole32!CoTaskMemFree` at `0x18008b70e`

## string_xrefs

- `0x18008b577`: `Security`
- `0x18008b4a3`: `ReadCredsFromRegistry`

## pseudocode

```c
__int64 __fastcall ReadCredsFromRegistry(unsigned __int16 **a1, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rbx
  __int16 v5; // ax
  int v6; // eax
  bool v7; // sf
  __int16 v8; // ax
  int v9; // eax
  _BYTE *v10; // r11
  __int64 v11; // rdi
  int v12; // eax
  __int16 v13; // ax
  __int16 v14; // ax
  __int64 v15; // r15
  __int64 v16; // rcx
  _BYTE *v17; // rax
  __int64 v18; // rax
  unsigned __int16 *v19; // rcx
  unsigned int v20; // ebx
  int phkResult; // [rsp+20h] [rbp-60h]
  int phkResulta; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  unsigned __int64 v25; // [rsp+38h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-40h] BYREF
  int v27; // [rsp+48h] [rbp-38h] BYREF
  __int16 v28; // [rsp+4Ch] [rbp-34h]
  __int16 v29; // [rsp+4Eh] [rbp-32h]
  unsigned int v30; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v31; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int16 *v32; // [rsp+D0h] [rbp+50h] BYREF
  HKEY v33; // [rsp+D8h] [rbp+58h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v27, "ReadCredsFromRegistry", 0x26Du, 1u);
  hKey = 0;
  v4 = 0;
  v32 = 0;
  v33 = 0;
  pv = 0;
  v30 = 0;
  v31 = 0;
  v25 = 0;
  if ( a1 )
    *a1 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = 635;
  if ( !a1 || (v28 = 635, v5 = 636, !a2) )
  {
    v27 = -2147024809;
    v29 = v5;
    goto LABEL_39;
  }
  v28 = 636;
  v27 = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsBackup",
         0,
         0x2001Fu,
         &hKey);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  v27 = v6;
  v7 = v6 < 0;
  v8 = 639;
  if ( !v7 )
  {
    v28 = 639;
    v9 = RegOpenKeyExW(hKey, L"Security", 0, 0x2001Fu, &v33);
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    v27 = v9;
    v7 = v9 < 0;
    v8 = 642;
    if ( !v7 )
    {
      v28 = 642;
      v27 = ReadBinaryFromRegistryEncrypted(
              v33,
              &c_wszSafedocsCredentialsUser,
              (unsigned __int8 **)&pv,
              &v30,
              phkResult);
      if ( v27 < 0 )
      {
        v10 = pv;
        LODWORD(v11) = v30;
        v29 = 644;
LABEL_27:
        if ( v10 )
        {
          v16 = (unsigned int)v11;
          v17 = v10;
          if ( (_DWORD)v11 )
          {
            do
            {
              *v17++ = 0;
              --v16;
            }
            while ( v16 );
          }
          CoTaskMemFree(v10);
        }
        if ( v4 )
        {
          v18 = v31;
          v19 = v4;
          if ( v31 )
          {
            do
            {
              *(_BYTE *)v19 = 0;
              v19 = (unsigned __int16 *)((char *)v19 + 1);
              --v18;
            }
            while ( v18 );
          }
          CoTaskMemFree(v4);
        }
        goto LABEL_35;
      }
      v28 = 644;
      v12 = ReadBinaryFromRegistryEncrypted(
              v33,
              &c_wszSafedocsCredentialsPassword,
              (unsigned __int8 **)&v32,
              &v31,
              phkResulta);
      v10 = pv;
      v7 = v12 < 0;
      v27 = v12;
      v13 = 645;
      if ( v7 )
      {
        LODWORD(v11) = v30;
LABEL_19:
        v4 = v32;
        v29 = v13;
        goto LABEL_27;
      }
      v11 = v30;
      v28 = 645;
      v27 = StringCbLengthW((const unsigned __int16 *)pv, v30, &v25);
      v13 = 648;
      if ( v27 < 0 )
        goto LABEL_19;
      v4 = v32;
      v28 = 648;
      v14 = 649;
      if ( v25 + 2 == v11 )
      {
        v15 = v31;
        v27 = 0;
        v28 = 649;
        v27 = StringCbLengthW(v32, v31, &v25);
        v14 = 650;
        if ( v27 < 0 )
          goto LABEL_23;
        v28 = 650;
        v14 = 651;
        if ( v25 + 2 == v15 )
        {
          *a1 = (unsigned __int16 *)v10;
          LODWORD(v11) = 0;
          *a2 = v4;
          v10 = 0;
          v4 = 0;
          v27 = 0;
          v28 = 651;
          v31 = 0;
          goto LABEL_27;
        }
      }
      v27 = -2147418113;
LABEL_23:
      v29 = v14;
      goto LABEL_27;
    }
  }
  v29 = v8;
LABEL_35:
  if ( v33 )
  {
    RegCloseKey(v33);
    v33 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
LABEL_39:
  v20 = v27;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v27);
  return v20;
}

```

## disassembly

```asm
0x18008b488  push    rbp
0x18008b48a  push    rbx
0x18008b48b  push    rsi
0x18008b48c  push    rdi
0x18008b48d  push    r12
0x18008b48f  push    r14
0x18008b491  push    r15
0x18008b493  mov     rbp, rsp
0x18008b496  sub     rsp, 80h
0x18008b49d  mov     rsi, rdx
0x18008b4a0  mov     r14, rcx
0x18008b4a3  lea     rdx, aReadcredsfromr; "ReadCredsFromRegistry"
0x18008b4aa  mov     r9d, 1; unsigned __int16
0x18008b4b0  lea     rcx, [rbp+var_38]; this
0x18008b4b4  mov     r8d, 26Dh; unsigned __int16
0x18008b4ba  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18008b4bf  xor     r12d, r12d
0x18008b4c2  mov     [rbp+hKey], r12
0x18008b4c6  mov     ebx, r12d
0x18008b4c9  mov     [rbp+arg_10], rbx
0x18008b4cd  mov     [rbp+arg_18], r12
0x18008b4d1  mov     [rbp+pv], r12
0x18008b4d5  mov     [rbp+arg_0], r12d
0x18008b4d9  mov     [rbp+arg_8], r12d
0x18008b4dd  mov     [rbp+var_48], r12
0x18008b4e1  test    r14, r14
0x18008b4e4  jz      short loc_18008B4E9
0x18008b4e6  mov     [r14], r12
0x18008b4e9  test    rsi, rsi
0x18008b4ec  jz      short loc_18008B4F1
0x18008b4ee  mov     [rsi], r12
0x18008b4f1  mov     eax, 27Bh
0x18008b4f6  test    r14, r14
0x18008b4f9  jnz     short loc_18008B50B
0x18008b4fb  mov     [rbp+var_38], 80070057h
0x18008b502  mov     [rbp+var_32], ax
0x18008b506  jmp     loc_18008B74C
0x18008b50b  mov     [rbp+var_34], ax
0x18008b50f  mov     eax, 27Ch
0x18008b514  test    rsi, rsi
0x18008b517  jz      short loc_18008B4FB
0x18008b519  mov     [rbp+var_34], ax
0x18008b51d  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18008b524  lea     rax, [rbp+hKey]
0x18008b528  mov     [rbp+var_38], r12d
0x18008b52c  mov     r15d, 2001Fh
0x18008b532  mov     qword ptr [rsp+80h+phkResult], rax; phkResult
0x18008b537  mov     r9d, r15d; samDesired
0x18008b53a  xor     r8d, r8d; ulOptions
0x18008b53d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008b544  call    cs:__imp_RegOpenKeyExW
0x18008b54b  nop     dword ptr [rax+rax+00h]
0x18008b550  mov     edi, 80070000h
0x18008b555  test    eax, eax
0x18008b557  jle     short loc_18008B55E
0x18008b559  movzx   eax, ax
0x18008b55c  or      eax, edi
0x18008b55e  mov     [rbp+var_38], eax
0x18008b561  test    eax, eax
0x18008b563  mov     eax, 27Fh
0x18008b568  jns     short loc_18008B573
0x18008b56a  mov     [rbp+var_32], ax
0x18008b56e  jmp     loc_18008B71A
0x18008b573  mov     rcx, [rbp+hKey]; hKey
0x18008b577  lea     rdx, c_wszSafedocsCredentialsKey; "Security"
0x18008b57e  mov     [rbp+var_34], ax
0x18008b582  mov     r9d, r15d; samDesired
0x18008b585  lea     rax, [rbp+arg_18]
0x18008b589  xor     r8d, r8d; ulOptions
0x18008b58c  mov     qword ptr [rsp+80h+phkResult], rax; int
0x18008b591  call    cs:__imp_RegOpenKeyExW
0x18008b598  nop     dword ptr [rax+rax+00h]
0x18008b59d  test    eax, eax
0x18008b59f  jle     short loc_18008B5A6
0x18008b5a1  movzx   eax, ax
0x18008b5a4  or      eax, edi
0x18008b5a6  mov     [rbp+var_38], eax
0x18008b5a9  test    eax, eax
0x18008b5ab  mov     eax, 282h
0x18008b5b0  js      short loc_18008B56A
0x18008b5b2  mov     rcx, [rbp+arg_18]; hKey
0x18008b5b6  lea     r9, [rbp+arg_0]; unsigned int *
0x18008b5ba  lea     r8, [rbp+pv]; unsigned __int8 **
0x18008b5be  mov     [rbp+var_34], ax
0x18008b5c2  lea     rdx, c_wszSafedocsCredentialsUser; lpValueName
0x18008b5c9  call    ?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z; ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)
0x18008b5ce  mov     [rbp+var_38], eax
0x18008b5d1  test    eax, eax
0x18008b5d3  mov     eax, 284h
0x18008b5d8  jns     short loc_18008B5EA
0x18008b5da  mov     r11, [rbp+pv]
0x18008b5de  mov     edi, [rbp+arg_0]
0x18008b5e1  mov     [rbp+var_32], ax
0x18008b5e5  jmp     loc_18008B6C6
0x18008b5ea  mov     rcx, [rbp+arg_18]; hKey
0x18008b5ee  lea     r9, [rbp+arg_8]; unsigned int *
0x18008b5f2  lea     r8, [rbp+arg_10]; unsigned __int8 **
0x18008b5f6  mov     [rbp+var_34], ax
0x18008b5fa  lea     rdx, c_wszSafedocsCredentialsPassword; lpValueName
0x18008b601  call    ?ReadBinaryFromRegistryEncrypted@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAKH@Z; ReadBinaryFromRegistryEncrypted(HKEY__ *,ushort const *,uchar * *,ulong *,int)
0x18008b606  mov     r11, [rbp+pv]
0x18008b60a  test    eax, eax
0x18008b60c  mov     [rbp+var_38], eax
0x18008b60f  mov     eax, 285h
0x18008b614  jns     short loc_18008B626
0x18008b616  mov     edi, [rbp+arg_0]
0x18008b619  mov     rbx, [rbp+arg_10]
0x18008b61d  mov     [rbp+var_32], ax
0x18008b621  jmp     loc_18008B6C6
0x18008b626  mov     edi, [rbp+arg_0]
0x18008b629  lea     r8, [rbp+var_48]; unsigned __int64 *
0x18008b62d  mov     edx, edi; unsigned __int64
0x18008b62f  mov     [rbp+var_34], ax
0x18008b633  mov     rcx, r11; unsigned __int16 *
0x18008b636  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008b63b  mov     [rbp+var_38], eax
0x18008b63e  test    eax, eax
0x18008b640  mov     eax, 288h
0x18008b645  js      short loc_18008B619
0x18008b647  mov     rbx, [rbp+arg_10]
0x18008b64b  mov     [rbp+var_34], ax
0x18008b64f  mov     rax, [rbp+var_48]
0x18008b653  add     rax, 2
0x18008b657  cmp     rax, rdi
0x18008b65a  mov     eax, 289h
0x18008b65f  jz      short loc_18008B66E
0x18008b661  mov     [rbp+var_38], 8000FFFFh
0x18008b668  mov     [rbp+var_32], ax
0x18008b66c  jmp     short loc_18008B6C6
0x18008b66e  mov     r15d, [rbp+arg_8]
0x18008b672  lea     r8, [rbp+var_48]; unsigned __int64 *
0x18008b676  mov     edx, r15d; unsigned __int64
0x18008b679  mov     [rbp+var_38], r12d
0x18008b67d  mov     rcx, rbx; unsigned __int16 *
0x18008b680  mov     [rbp+var_34], ax
0x18008b684  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008b689  mov     [rbp+var_38], eax
0x18008b68c  test    eax, eax
0x18008b68e  mov     eax, 28Ah
0x18008b693  js      short loc_18008B668
0x18008b695  mov     [rbp+var_34], ax
0x18008b699  mov     rax, [rbp+var_48]
0x18008b69d  add     rax, 2
0x18008b6a1  cmp     rax, r15
0x18008b6a4  mov     eax, 28Bh
0x18008b6a9  jnz     short loc_18008B661
0x18008b6ab  mov     [r14], r11
0x18008b6ae  mov     edi, r12d
0x18008b6b1  mov     [rsi], rbx
0x18008b6b4  mov     r11, r12
0x18008b6b7  mov     rbx, r12
0x18008b6ba  mov     [rbp+var_38], r12d
0x18008b6be  mov     [rbp+var_34], ax
0x18008b6c2  mov     [rbp+arg_8], r12d
0x18008b6c6  test    r11, r11
0x18008b6c9  jz      short loc_18008B6EF
0x18008b6cb  mov     ecx, edi
0x18008b6cd  mov     rax, r11
0x18008b6d0  test    edi, edi
0x18008b6d2  jz      short loc_18008B6E0
0x18008b6d4  mov     [rax], r12b
0x18008b6d7  inc     rax
0x18008b6da  sub     rcx, 1
0x18008b6de  jnz     short loc_18008B6D4
0x18008b6e0  mov     rcx, r11; pv
0x18008b6e3  call    cs:__imp_CoTaskMemFree
0x18008b6ea  nop     dword ptr [rax+rax+00h]
0x18008b6ef  test    rbx, rbx
0x18008b6f2  jz      short loc_18008B71A
0x18008b6f4  mov     eax, [rbp+arg_8]
0x18008b6f7  mov     rcx, rbx
0x18008b6fa  test    rax, rax
0x18008b6fd  jz      short loc_18008B70B
0x18008b6ff  mov     [rcx], r12b
0x18008b702  inc     rcx
0x18008b705  sub     rax, 1
0x18008b709  jnz     short loc_18008B6FF
0x18008b70b  mov     rcx, rbx; pv
0x18008b70e  call    cs:__imp_CoTaskMemFree
0x18008b715  nop     dword ptr [rax+rax+00h]
0x18008b71a  mov     rcx, [rbp+arg_18]; hKey
0x18008b71e  test    rcx, rcx
0x18008b721  jz      short loc_18008B733
0x18008b723  call    cs:__imp_RegCloseKey
0x18008b72a  nop     dword ptr [rax+rax+00h]
0x18008b72f  mov     [rbp+arg_18], r12
0x18008b733  mov     rcx, [rbp+hKey]; hKey
0x18008b737  test    rcx, rcx
0x18008b73a  jz      short loc_18008B74C
0x18008b73c  call    cs:__imp_RegCloseKey
0x18008b743  nop     dword ptr [rax+rax+00h]
0x18008b748  mov     [rbp+hKey], r12
0x18008b74c  mov     ebx, [rbp+var_38]
0x18008b74f  lea     rcx, [rbp+var_38]; this
0x18008b753  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18008b758  mov     eax, ebx
0x18008b75a  add     rsp, 80h
0x18008b761  pop     r15
0x18008b763  pop     r14
0x18008b765  pop     r12
0x18008b767  pop     rdi
0x18008b768  pop     rsi
0x18008b769  pop     rbx
0x18008b76a  pop     rbp
0x18008b76b  retn
```
