# CopyUserStructure(_USER_ALL_INFORMATION * const,_USER_ALL_INFORMATION * *)

- ea: `0x180002670`
- end: `0x180002bb6`
- name: `?CopyUserStructure@@YAJQEAU_USER_ALL_INFORMATION@@PEAPEAU1@@Z`
- size: `1350`
- prototype: `__int64 __fastcall(struct _USER_ALL_INFORMATION *const, struct _USER_ALL_INFORMATION **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180002670`
- `0x1800039e0`
- `0x180003a60`
- `0x180007300`
- `0x18000cb84`
- `0x180012f18`
- `0x180016ce9`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000269f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002aba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000269f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800028db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002aba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002b21`

## pseudocode

```c
__int64 __fastcall CopyUserStructure(struct _USER_ALL_INFORMATION *const a1, struct _USER_ALL_INFORMATION **a2)
{
  struct _USER_ALL_INFORMATION *v4; // rax
  struct _USER_ALL_INFORMATION *v5; // rsi
  size_t v6; // rax
  int v7; // edi
  SIZE_T MaximumLength; // r12
  WCHAR *v9; // rcx
  ULONG Length; // eax
  UCHAR *v11; // rax
  SIZE_T v12; // rbp
  UCHAR *v13; // rax

  if ( !a1 || !a2 )
  {
    v7 = -2147467261;
    v5 = 0;
    goto LABEL_88;
  }
  v4 = (struct _USER_ALL_INFORMATION *)CoTaskMemAlloc(0x13Cu);
  v5 = v4;
  if ( !v4 )
    goto LABEL_77;
  v6 = CTCoAllocPolicy::_CoTaskMemSize(v4);
  memset_0(v5, 0, v6);
  v5->LastLogon.QuadPart = a1->LastLogon.QuadPart;
  v5->LastLogoff.QuadPart = a1->LastLogoff.QuadPart;
  v5->PasswordLastSet.QuadPart = a1->PasswordLastSet.QuadPart;
  v5->AccountExpires.QuadPart = a1->AccountExpires.QuadPart;
  v5->PasswordCanChange.QuadPart = a1->PasswordCanChange.QuadPart;
  v5->PasswordMustChange.QuadPart = a1->PasswordMustChange.QuadPart;
  v5->UserId = a1->UserId;
  v5->PrimaryGroupId = a1->PrimaryGroupId;
  v5->UserAccountControl = a1->UserAccountControl;
  v5->WhichFields = a1->WhichFields;
  v5->BadPasswordCount = a1->BadPasswordCount;
  v5->LogonCount = a1->LogonCount;
  v5->CountryCode = a1->CountryCode;
  v5->CodePage = a1->CodePage;
  v5->LmPasswordPresent = a1->LmPasswordPresent;
  v5->NtPasswordPresent = a1->NtPasswordPresent;
  v5->PasswordExpired = a1->PasswordExpired;
  v5->PrivateDataSensitive = a1->PrivateDataSensitive;
  if ( a1->UserName.Length && a1->UserName.Buffer )
  {
    v7 = CopyUnicodeStringAlloc(&a1->UserName, &v5->UserName);
    if ( v7 < 0 )
      goto LABEL_88;
  }
  else
  {
    v7 = 0;
    *(_DWORD *)&v5->UserName.Length = 0;
    v5->UserName.Buffer = 0;
  }
  if ( a1->FullName.Length && a1->FullName.Buffer )
  {
    v7 = CopyUnicodeStringAlloc(&a1->FullName, &v5->FullName);
    if ( v7 < 0 )
      goto LABEL_88;
  }
  else
  {
    *(_DWORD *)&v5->FullName.Length = 0;
    v5->FullName.Buffer = 0;
  }
  if ( a1->HomeDirectory.Length && a1->HomeDirectory.Buffer )
  {
    v7 = CopyUnicodeStringAlloc(&a1->HomeDirectory, &v5->HomeDirectory);
    if ( v7 < 0 )
      goto LABEL_88;
  }
  else
  {
    *(_DWORD *)&v5->HomeDirectory.Length = 0;
    v5->HomeDirectory.Buffer = 0;
  }
  if ( a1->HomeDirectoryDrive.Length && a1->HomeDirectoryDrive.Buffer )
  {
    v7 = CopyUnicodeStringAlloc(&a1->HomeDirectoryDrive, &v5->HomeDirectoryDrive);
    if ( v7 < 0 )
      goto LABEL_88;
  }
  else
  {
    *(_DWORD *)&v5->HomeDirectoryDrive.Length = 0;
    v5->HomeDirectoryDrive.Buffer = 0;
  }
  if ( a1->ScriptPath.Length && a1->ScriptPath.Buffer )
  {
    v7 = CopyUnicodeStringAlloc(&a1->ScriptPath, &v5->ScriptPath);
    if ( v7 < 0 )
      goto LABEL_88;
  }
  else
  {
    *(_DWORD *)&v5->ScriptPath.Length = 0;
    v5->ScriptPath.Buffer = 0;
  }
  if ( !a1->ProfilePath.Length || !a1->ProfilePath.Buffer )
  {
    *(_DWORD *)&v5->ProfilePath.Length = 0;
    v5->ProfilePath.Buffer = 0;
LABEL_34:
    if ( a1->AdminComment.Length && a1->AdminComment.Buffer )
    {
      if ( v5 == (struct _USER_ALL_INFORMATION *)-144LL )
      {
        v7 = -2147467261;
      }
      else
      {
        MaximumLength = a1->AdminComment.MaximumLength;
        v9 = (WCHAR *)CoTaskMemAlloc(MaximumLength);
        if ( v9 )
        {
          v5->AdminComment.Length = a1->AdminComment.Length;
          v7 = 0;
          v5->AdminComment.MaximumLength = a1->AdminComment.MaximumLength;
          v5->AdminComment.Buffer = v9;
          memcpy_0(v9, a1->AdminComment.Buffer, MaximumLength);
        }
        else
        {
          v7 = -2147024882;
        }
      }
      if ( v7 < 0 )
        goto LABEL_88;
    }
    else
    {
      *(_DWORD *)&v5->AdminComment.Length = 0;
      v5->AdminComment.Buffer = 0;
    }
    if ( a1->WorkStations.Length && a1->WorkStations.Buffer )
    {
      v7 = CopyUnicodeStringAlloc(&a1->WorkStations, &v5->WorkStations);
      if ( v7 < 0 )
        goto LABEL_88;
    }
    else
    {
      *(_DWORD *)&v5->WorkStations.Length = 0;
      v5->WorkStations.Buffer = 0;
    }
    if ( a1->UserComment.Length && a1->UserComment.Buffer )
    {
      v7 = CopyUnicodeStringAlloc(&a1->UserComment, &v5->UserComment);
      if ( v7 < 0 )
        goto LABEL_88;
    }
    else
    {
      *(_DWORD *)&v5->UserComment.Length = 0;
      v5->UserComment.Buffer = 0;
    }
    if ( a1->Parameters.Length && a1->Parameters.Buffer )
    {
      v7 = CopyUnicodeStringAlloc(&a1->Parameters, &v5->Parameters);
      if ( v7 < 0 )
        goto LABEL_88;
    }
    else
    {
      *(_DWORD *)&v5->Parameters.Length = 0;
      v5->Parameters.Buffer = 0;
    }
    if ( a1->LmPassword.Length && a1->LmPassword.Buffer )
    {
      v7 = CopyUnicodeStringAlloc(&a1->LmPassword, &v5->LmPassword);
      if ( v7 < 0 )
        goto LABEL_88;
    }
    else
    {
      *(_DWORD *)&v5->LmPassword.Length = 0;
      v5->LmPassword.Buffer = 0;
    }
    if ( a1->NtPassword.Length && a1->NtPassword.Buffer )
    {
      v7 = CopyUnicodeStringAlloc(&a1->NtPassword, &v5->NtPassword);
      if ( v7 < 0 )
        goto LABEL_88;
    }
    else
    {
      *(_DWORD *)&v5->NtPassword.Length = 0;
      v5->NtPassword.Buffer = 0;
    }
    if ( a1->PrivateData.Length && a1->PrivateData.Buffer )
    {
      v7 = CopyUnicodeStringAlloc(&a1->PrivateData, &v5->PrivateData);
      if ( v7 < 0 )
        goto LABEL_88;
    }
    else
    {
      *(_DWORD *)&v5->PrivateData.Length = 0;
      v5->PrivateData.Buffer = 0;
    }
    v5->SecurityDescriptor.Length = a1->SecurityDescriptor.Length;
    Length = a1->SecurityDescriptor.Length;
    if ( Length && a1->SecurityDescriptor.SecurityDescriptor )
    {
      v11 = (UCHAR *)CoTaskMemAlloc(Length);
      v5->SecurityDescriptor.SecurityDescriptor = v11;
      if ( !v11 )
      {
LABEL_77:
        v7 = -2147024882;
        goto LABEL_88;
      }
      memcpy_0(v11, a1->SecurityDescriptor.SecurityDescriptor, a1->SecurityDescriptor.Length);
    }
    else
    {
      v5->SecurityDescriptor.SecurityDescriptor = 0;
    }
    v5->LogonHours.UnitsPerWeek = a1->LogonHours.UnitsPerWeek;
    if ( a1->LogonHours.UnitsPerWeek && a1->LogonHours.LogonHours )
    {
      v12 = (unsigned __int64)a1->LogonHours.UnitsPerWeek >> 3;
      v13 = (UCHAR *)CoTaskMemAlloc(v12);
      v5->LogonHours.LogonHours = v13;
      if ( !v13 )
      {
        v7 = -2147024882;
        goto LABEL_88;
      }
      memcpy_0(v13, a1->LogonHours.LogonHours, v12);
    }
    else
    {
      v5->LogonHours.LogonHours = 0;
    }
    *a2 = v5;
    return (unsigned int)v7;
  }
  v7 = CopyUnicodeStringAlloc(&a1->ProfilePath, &v5->ProfilePath);
  if ( v7 >= 0 )
    goto LABEL_34;
LABEL_88:
  FreeUserStructure(v5, 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002670  mov     [rsp+arg_10], rbx
0x180002675  mov     [rsp+arg_18], rbp
0x18000267a  push    rsi
0x18000267b  push    rdi
0x18000267c  push    r14
0x18000267e  sub     rsp, 20h
0x180002682  mov     r14, rdx
0x180002685  mov     rbx, rcx
0x180002688  test    rcx, rcx
0x18000268b  jz      loc_180002B5A
0x180002691  test    rdx, rdx
0x180002694  jz      loc_180002B5A
0x18000269a  mov     ecx, 13Ch; cb
0x18000269f  call    cs:__imp_CoTaskMemAlloc
0x1800026a5  mov     rsi, rax
0x1800026a8  test    rax, rax
0x1800026ab  jz      loc_180002ACC
0x1800026b1  mov     rcx, rax; void *
0x1800026b4  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x1800026b9  mov     r8, rax; Size
0x1800026bc  xor     edx, edx; Val
0x1800026be  mov     rcx, rsi; void *
0x1800026c1  call    memset_0
0x1800026c6  mov     rax, [rbx]
0x1800026c9  lea     rcx, [rbx+30h]; struct _UNICODE_STRING *
0x1800026cd  mov     [rsi], rax
0x1800026d0  xor     ebp, ebp
0x1800026d2  mov     rax, [rbx+8]
0x1800026d6  mov     [rsi+8], rax
0x1800026da  mov     rax, [rbx+10h]
0x1800026de  mov     [rsi+10h], rax
0x1800026e2  mov     rax, [rbx+18h]
0x1800026e6  mov     [rsi+18h], rax
0x1800026ea  mov     rax, [rbx+20h]
0x1800026ee  mov     [rsi+20h], rax
0x1800026f2  mov     rax, [rbx+28h]
0x1800026f6  mov     [rsi+28h], rax
0x1800026fa  mov     eax, [rbx+110h]
0x180002700  mov     [rsi+110h], eax
0x180002706  mov     eax, [rbx+114h]
0x18000270c  mov     [rsi+114h], eax
0x180002712  mov     eax, [rbx+118h]
0x180002718  mov     [rsi+118h], eax
0x18000271e  mov     eax, [rbx+11Ch]
0x180002724  mov     [rsi+11Ch], eax
0x18000272a  movzx   eax, word ptr [rbx+130h]
0x180002731  mov     [rsi+130h], ax
0x180002738  movzx   eax, word ptr [rbx+132h]
0x18000273f  mov     [rsi+132h], ax
0x180002746  movzx   eax, word ptr [rbx+134h]
0x18000274d  mov     [rsi+134h], ax
0x180002754  movzx   eax, word ptr [rbx+136h]
0x18000275b  mov     [rsi+136h], ax
0x180002762  movzx   eax, byte ptr [rbx+138h]
0x180002769  mov     [rsi+138h], al
0x18000276f  movzx   eax, byte ptr [rbx+139h]
0x180002776  mov     [rsi+139h], al
0x18000277c  movzx   eax, byte ptr [rbx+13Ah]
0x180002783  mov     [rsi+13Ah], al
0x180002789  movzx   eax, byte ptr [rbx+13Bh]
0x180002790  mov     [rsi+13Bh], al
0x180002796  cmp     [rcx], bp
0x180002799  jbe     short loc_1800027B5
0x18000279b  cmp     [rbx+38h], rbp
0x18000279f  jz      short loc_1800027B5
0x1800027a1  lea     rdx, [rsi+30h]; struct _UNICODE_STRING *
0x1800027a5  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x1800027aa  mov     edi, eax
0x1800027ac  test    eax, eax
0x1800027ae  jns     short loc_1800027BE
0x1800027b0  jmp     loc_180002B63
0x1800027b5  mov     edi, ebp
0x1800027b7  mov     [rsi+30h], ebp
0x1800027ba  mov     [rsi+38h], rbp
0x1800027be  cmp     [rbx+40h], bp
0x1800027c2  lea     rcx, [rbx+40h]; struct _UNICODE_STRING *
0x1800027c6  jbe     short loc_1800027E2
0x1800027c8  cmp     [rbx+48h], rbp
0x1800027cc  jz      short loc_1800027E2
0x1800027ce  lea     rdx, [rsi+40h]; struct _UNICODE_STRING *
0x1800027d2  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x1800027d7  mov     edi, eax
0x1800027d9  test    eax, eax
0x1800027db  jns     short loc_1800027E9
0x1800027dd  jmp     loc_180002B63
0x1800027e2  mov     [rsi+40h], ebp
0x1800027e5  mov     [rsi+48h], rbp
0x1800027e9  cmp     [rbx+50h], bp
0x1800027ed  lea     rcx, [rbx+50h]; struct _UNICODE_STRING *
0x1800027f1  jbe     short loc_18000280D
0x1800027f3  cmp     [rbx+58h], rbp
0x1800027f7  jz      short loc_18000280D
0x1800027f9  lea     rdx, [rsi+50h]; struct _UNICODE_STRING *
0x1800027fd  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180002802  mov     edi, eax
0x180002804  test    eax, eax
0x180002806  jns     short loc_180002814
0x180002808  jmp     loc_180002B63
0x18000280d  mov     [rsi+50h], ebp
0x180002810  mov     [rsi+58h], rbp
0x180002814  cmp     [rbx+60h], bp
0x180002818  lea     rcx, [rbx+60h]; struct _UNICODE_STRING *
0x18000281c  jbe     short loc_180002838
0x18000281e  cmp     [rbx+68h], rbp
0x180002822  jz      short loc_180002838
0x180002824  lea     rdx, [rsi+60h]; struct _UNICODE_STRING *
0x180002828  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x18000282d  mov     edi, eax
0x18000282f  test    eax, eax
0x180002831  jns     short loc_18000283F
0x180002833  jmp     loc_180002B63
0x180002838  mov     [rsi+60h], ebp
0x18000283b  mov     [rsi+68h], rbp
0x18000283f  cmp     [rbx+70h], bp
0x180002843  lea     rcx, [rbx+70h]; struct _UNICODE_STRING *
0x180002847  jbe     short loc_180002863
0x180002849  cmp     [rbx+78h], rbp
0x18000284d  jz      short loc_180002863
0x18000284f  lea     rdx, [rsi+70h]; struct _UNICODE_STRING *
0x180002853  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180002858  mov     edi, eax
0x18000285a  test    eax, eax
0x18000285c  jns     short loc_18000286A
0x18000285e  jmp     loc_180002B63
0x180002863  mov     [rsi+70h], ebp
0x180002866  mov     [rsi+78h], rbp
0x18000286a  lea     rcx, [rbx+80h]; struct _UNICODE_STRING *
0x180002871  cmp     [rcx], bp
0x180002874  jbe     short loc_180002897
0x180002876  cmp     [rbx+88h], rbp
0x18000287d  jz      short loc_180002897
0x18000287f  lea     rdx, [rsi+80h]; struct _UNICODE_STRING *
0x180002886  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x18000288b  mov     edi, eax
0x18000288d  test    eax, eax
0x18000288f  js      loc_180002B63
0x180002895  jmp     short loc_1800028A4
0x180002897  mov     [rsi+80h], ebp
0x18000289d  mov     [rsi+88h], rbp
0x1800028a4  cmp     [rbx+90h], bp
0x1800028ab  jbe     loc_180002936
0x1800028b1  cmp     [rbx+98h], rbp
0x1800028b8  jz      short loc_180002936
0x1800028ba  mov     [rsp+38h+arg_8], r15
0x1800028bf  lea     r15, [rsi+90h]
0x1800028c6  mov     [rsp+38h+arg_0], r12
0x1800028cb  test    r15, r15
0x1800028ce  jz      short loc_18000291E
0x1800028d0  movzx   r12d, word ptr [rbx+92h]
0x1800028d8  mov     ecx, r12d; cb
0x1800028db  call    cs:__imp_CoTaskMemAlloc
0x1800028e1  mov     rcx, rax; void *
0x1800028e4  test    rax, rax
0x1800028e7  jnz     short loc_1800028F0
0x1800028e9  mov     edi, 8007000Eh
0x1800028ee  jmp     short loc_180002923
0x1800028f0  movzx   eax, word ptr [rbx+90h]
0x1800028f7  mov     r8, r12; Size
0x1800028fa  mov     [r15], ax
0x1800028fe  mov     edi, ebp
0x180002900  movzx   eax, word ptr [rbx+92h]
0x180002907  mov     [r15+2], ax
0x18000290c  mov     [r15+8], rcx
0x180002910  mov     rdx, [rbx+98h]; Src
0x180002917  call    memcpy_0
0x18000291c  jmp     short loc_180002923
0x18000291e  mov     edi, 80004003h
0x180002923  mov     r15, [rsp+38h+arg_8]
0x180002928  mov     r12, [rsp+38h+arg_0]
0x18000292d  test    edi, edi
0x18000292f  jns     short loc_180002943
0x180002931  jmp     loc_180002B63
0x180002936  mov     [rsi+90h], ebp
0x18000293c  mov     [rsi+98h], rbp
0x180002943  lea     rcx, [rbx+0A0h]; struct _UNICODE_STRING *
0x18000294a  cmp     [rcx], bp
0x18000294d  jbe     short loc_18000296F
0x18000294f  cmp     [rbx+0A8h], rbp
0x180002956  jz      short loc_18000296F
0x180002958  lea     rdx, [rsi+0A0h]; struct _UNICODE_STRING *
0x18000295f  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180002964  mov     edi, eax
0x180002966  test    eax, eax
0x180002968  jns     short loc_18000297C
0x18000296a  jmp     loc_180002B63
0x18000296f  mov     [rsi+0A0h], ebp
0x180002975  mov     [rsi+0A8h], rbp
0x18000297c  lea     rcx, [rbx+0B0h]; struct _UNICODE_STRING *
0x180002983  cmp     [rcx], bp
0x180002986  jbe     short loc_1800029A8
0x180002988  cmp     [rbx+0B8h], rbp
0x18000298f  jz      short loc_1800029A8
0x180002991  lea     rdx, [rsi+0B0h]; struct _UNICODE_STRING *
0x180002998  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x18000299d  mov     edi, eax
0x18000299f  test    eax, eax
0x1800029a1  jns     short loc_1800029B5
0x1800029a3  jmp     loc_180002B63
0x1800029a8  mov     [rsi+0B0h], ebp
0x1800029ae  mov     [rsi+0B8h], rbp
0x1800029b5  lea     rcx, [rbx+0C0h]; struct _UNICODE_STRING *
0x1800029bc  cmp     [rcx], bp
0x1800029bf  jbe     short loc_1800029E1
0x1800029c1  cmp     [rbx+0C8h], rbp
0x1800029c8  jz      short loc_1800029E1
0x1800029ca  lea     rdx, [rsi+0C0h]; struct _UNICODE_STRING *
0x1800029d1  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x1800029d6  mov     edi, eax
0x1800029d8  test    eax, eax
0x1800029da  jns     short loc_1800029EE
0x1800029dc  jmp     loc_180002B63
0x1800029e1  mov     [rsi+0C0h], ebp
0x1800029e7  mov     [rsi+0C8h], rbp
0x1800029ee  lea     rcx, [rbx+0D0h]; struct _UNICODE_STRING *
0x1800029f5  cmp     [rcx], bp
0x1800029f8  jbe     short loc_180002A1A
0x1800029fa  cmp     [rbx+0D8h], rbp
0x180002a01  jz      short loc_180002A1A
0x180002a03  lea     rdx, [rsi+0D0h]; struct _UNICODE_STRING *
0x180002a0a  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180002a0f  mov     edi, eax
0x180002a11  test    eax, eax
0x180002a13  jns     short loc_180002A27
0x180002a15  jmp     loc_180002B63
0x180002a1a  mov     [rsi+0D0h], ebp
0x180002a20  mov     [rsi+0D8h], rbp
0x180002a27  lea     rcx, [rbx+0E0h]; struct _UNICODE_STRING *
0x180002a2e  cmp     [rcx], bp
0x180002a31  jbe     short loc_180002A53
0x180002a33  cmp     [rbx+0E8h], rbp
0x180002a3a  jz      short loc_180002A53
0x180002a3c  lea     rdx, [rsi+0E0h]; struct _UNICODE_STRING *
0x180002a43  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180002a48  mov     edi, eax
0x180002a4a  test    eax, eax
0x180002a4c  jns     short loc_180002A60
0x180002a4e  jmp     loc_180002B63
0x180002a53  mov     [rsi+0E0h], ebp
0x180002a59  mov     [rsi+0E8h], rbp
0x180002a60  lea     rcx, [rbx+0F0h]; struct _UNICODE_STRING *
0x180002a67  cmp     [rcx], bp
0x180002a6a  jbe     short loc_180002A8C
0x180002a6c  cmp     [rbx+0F8h], rbp
0x180002a73  jz      short loc_180002A8C
0x180002a75  lea     rdx, [rsi+0F0h]; struct _UNICODE_STRING *
0x180002a7c  call    ?CopyUnicodeStringAlloc@@YAJQEAU_UNICODE_STRING@@PEAU1@@Z; CopyUnicodeStringAlloc(_UNICODE_STRING * const,_UNICODE_STRING *)
0x180002a81  mov     edi, eax
0x180002a83  test    eax, eax
0x180002a85  jns     short loc_180002A99
0x180002a87  jmp     loc_180002B63
0x180002a8c  mov     [rsi+0F0h], ebp
0x180002a92  mov     [rsi+0F8h], rbp
0x180002a99  mov     eax, [rbx+100h]
0x180002a9f  mov     [rsi+100h], eax
0x180002aa5  mov     eax, [rbx+100h]
0x180002aab  test    eax, eax
0x180002aad  jz      short loc_180002AEE
0x180002aaf  cmp     [rbx+108h], rbp
0x180002ab6  jz      short loc_180002AEE
0x180002ab8  mov     ecx, eax; cb
0x180002aba  call    cs:__imp_CoTaskMemAlloc
0x180002ac0  mov     [rsi+108h], rax
0x180002ac7  test    rax, rax
0x180002aca  jnz     short loc_180002AD6
0x180002acc  mov     edi, 8007000Eh
0x180002ad1  jmp     loc_180002B63
0x180002ad6  mov     r8d, [rbx+100h]; Size
0x180002add  mov     rcx, rax; void *
0x180002ae0  mov     rdx, [rbx+108h]; Src
0x180002ae7  call    memcpy_0
0x180002aec  jmp     short loc_180002AF5
0x180002aee  mov     [rsi+108h], rbp
0x180002af5  movzx   eax, word ptr [rbx+120h]
0x180002afc  mov     [rsi+120h], ax
0x180002b03  movzx   eax, word ptr [rbx+120h]
0x180002b0a  test    ax, ax
0x180002b0d  jz      short loc_180002B4E
0x180002b0f  cmp     [rbx+128h], rbp
0x180002b16  jz      short loc_180002B4E
0x180002b18  mov     ebp, eax
0x180002b1a  shr     rbp, 3
0x180002b1e  mov     rcx, rbp; cb
0x180002b21  call    cs:__imp_CoTaskMemAlloc
0x180002b27  mov     [rsi+128h], rax
0x180002b2e  test    rax, rax
0x180002b31  jnz     short loc_180002B3A
0x180002b33  mov     edi, 8007000Eh
0x180002b38  jmp     short loc_180002B63
0x180002b3a  mov     rdx, [rbx+128h]; Src
0x180002b41  mov     r8, rbp; Size
0x180002b44  mov     rcx, rax; void *
0x180002b47  call    memcpy_0
0x180002b4c  jmp     short loc_180002B55
0x180002b4e  mov     [rsi+128h], rbp
0x180002b55  mov     [r14], rsi
0x180002b58  jmp     short loc_180002BA1
0x180002b5a  xor     ebp, ebp
0x180002b5c  mov     edi, 80004003h
0x180002b61  mov     esi, ebp
0x180002b63  mov     edx, 1; int
  ... truncated ...
```
