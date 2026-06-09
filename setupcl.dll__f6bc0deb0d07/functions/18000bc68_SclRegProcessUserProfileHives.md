# SclRegProcessUserProfileHives

- ea: `0x18000bc68`
- end: `0x18000c214`
- name: `SclRegProcessUserProfileHives`
- size: `1452`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, const WCHAR *, const wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800111bc`
- `0x1800117e4`

## callees

- `0x1800014e8`
- `0x180001cd4`
- `0x180007df8`
- `0x1800091c0`
- `0x18000952c`
- `0x18000a4a0`
- `0x18000a524`
- `0x18000b738`
- `0x18000bc68`
- `0x18000d220`
- `0x18000e66c`
- `0x1800179e0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000bd29`
- `ntdll!RtlAllocateHeap` at `0x18000bd29`
- `ntdll!NtClose` at `0x18000c0ab`
- `ntdll!NtClose` at `0x18000c1bc`
- `ntdll!NtClose` at `0x18000c1cc`
- `ntdll!NtClose` at `0x18000c0ab`
- `ntdll!NtClose` at `0x18000c1bc`
- `ntdll!NtClose` at `0x18000c1cc`
- `ntdll!RtlFreeHeap` at `0x18000c082`
- `ntdll!RtlFreeHeap` at `0x18000c1a7`
- `ntdll!RtlFreeHeap` at `0x18000c1e9`
- `ntdll!RtlFreeHeap` at `0x18000c082`
- `ntdll!RtlFreeHeap` at `0x18000c1a7`
- `ntdll!RtlFreeHeap` at `0x18000c1e9`

## string_xrefs

- `0x18000bdce`: `PATHNAME`
- `0x18000bdf3`: `PATHNAME`
- `0x18000bec0`: `(%lx): Failure during enumeration of subkeys.`
- `0x18000bd7a`: `(%lx): Failed to open PROFILELIST key.`
- `0x18000bf38`: `PROFILEIMAGEPATH`

## pseudocode

```c
__int64 __fastcall SclRegProcessUserProfileHives(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        const WCHAR *a4,
        const wchar_t *a5,
        __int64 a6)
{
  __int64 v6; // r13
  WCHAR *v10; // rdi
  int String; // ebx
  __int64 v12; // r8
  int Key; // eax
  int i; // esi
  int v15; // eax
  int v16; // edx
  __int64 v17; // rcx
  const WCHAR *v18; // rdx
  __int64 v19; // r14
  unsigned int v20; // r15d
  WCHAR *v21; // rsi
  __int64 v22; // r15
  WCHAR *v23; // rdi
  int v25; // [rsp+44h] [rbp-BCh]
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE v28; // [rsp+58h] [rbp-A8h] BYREF
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  const WCHAR *Heap; // [rsp+68h] [rbp-98h] BYREF
  HANDLE KeyHandle; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+88h] [rbp-78h]
  const wchar_t *v35; // [rsp+90h] [rbp-70h]
  const wchar_t *v36; // [rsp+98h] [rbp-68h]
  _BYTE v37[8]; // [rsp+A0h] [rbp-60h]
  const wchar_t *v38; // [rsp+A8h] [rbp-58h]
  char v39; // [rsp+B0h] [rbp-50h]
  WCHAR v40[784]; // [rsp+C0h] [rbp-40h] BYREF

  v6 = a1 + 1152;
  v35 = a5;
  v33 = a1;
  v34 = a6;
  v28 = 0;
  if ( !a1 )
    v6 = 0;
  KeyHandle = 0;
  v32 = 0;
  SclLogGenericMessage(
    v6,
    1,
    (int)SclEvent_Generic_Info,
    1488,
    (__int64)"SclRegProcessUserProfileHives",
    "Operating on user-specific profile hives...");
  v27 = 2064;
  Heap = (const WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x810u);
  v10 = (WCHAR *)Heap;
  if ( Heap )
  {
    Key = SclCreateKey(a2, a3, 0xF003Fu, (__int64)&v28);
    String = Key;
    if ( Key >= 0 )
    {
      String = SclCreateKey(a2, a4, 0xF003Fu, (__int64)&KeyHandle);
      if ( String >= 0 )
        String = SclRegValueExists(KeyHandle);
    }
    else
    {
      SclLogGenericMessage(
        v6,
        3,
        (int)SclEvent_Generic_Error,
        1508,
        (__int64)"SclRegProcessUserProfileHives",
        "(%lx): Failed to open PROFILELIST key.",
        Key);
    }
  }
  else
  {
    String = -1073741801;
    SclLogGenericMessage(
      v6,
      3,
      (int)SclEvent_Generic_Error,
      1498,
      (__int64)"SclRegProcessUserProfileHives",
      "(%lx): Could not allocate memory.",
      -1073741801);
  }
  for ( i = 0; ; ++i )
  {
    v25 = i;
    if ( String < 0 )
      break;
    LODWORD(P) = 0;
    Handle = 0;
    v15 = SclRegEnumerateKey((__int64)v28, i, v12, (int)&Heap, (__int64)&v27, 2, (__int64)&P);
    String = v15;
    if ( v15 == -2147483622 )
    {
      Handle = 0;
      String = SclRegGetString(v28, 0, (__int64)L"Default", v40, 0x30Cu);
      if ( String >= 0 )
      {
        String = RtlStringCchCatW(v40, 780, L"\\NTUSER.DAT");
        if ( String >= 0 )
        {
          v22 = v33;
          String = SclpRegExpandProfileHivePath(v33, v40, v35, v34, v32, (PWSTR *)&Handle);
          if ( String >= 0 )
          {
            v23 = (WCHAR *)Handle;
            if ( SclFileObjectExists((const WCHAR *)Handle) )
              String = SclRegProcessProfileHive(v22, v23);
            else
              SclLogGenericMessage(
                v6,
                3,
                (int)SclEvent_Generic_Error,
                1727,
                (__int64)"SclRegProcessUserProfileHives",
                "Default user profile hive does not exist, skipping: [%ws].",
                v23);
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v23);
          }
        }
      }
      v10 = (WCHAR *)Heap;
      break;
    }
    v10 = (WCHAR *)Heap;
    if ( v15 >= 0 )
    {
      v16 = *((_DWORD *)Heap + 3);
      if ( (unsigned __int64)(unsigned int)(v16 + 16) + 2 > v27 )
      {
        String = -2147483643;
      }
      else
      {
        v17 = v16 & 0xFFFFFFFE;
        v18 = Heap + 8;
        *(const WCHAR *)((char *)Heap + v17 + 16) = 0;
        String = SclCreateKey((__int64)v28, v18, 0xF003Fu, (__int64)&Handle);
        if ( String >= 0 && (int)SclRegGetString(Handle, 0, (__int64)L"PROFILEIMAGEPATH", v40, 0x30Cu) >= 0 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v40[v19] );
          v37[0] = 1;
          v36 = L"\\NTUSER.DAT";
          v20 = 0;
          v39 = 0;
          v38 = L"\\AppData\\Local\\Microsoft\\Windows\\UsrClass.dat";
          do
          {
            if ( v20 >= 2 )
              break;
            P = 0;
            String = RtlStringCchCopyW(&v40[v19], 780 - v19, *(_WORD **)&v37[16 * v20 - 8]);
            if ( String >= 0 )
            {
              String = SclpRegExpandProfileHivePath(v33, v40, v35, v34, v32, (PWSTR *)&P);
              if ( String >= 0 )
              {
                v21 = (WCHAR *)P;
                if ( SclFileObjectExists((const WCHAR *)P) )
                {
                  String = SclRegProcessProfileHive(v33, v21);
                }
                else if ( v37[16 * v20] )
                {
                  SclLogGenericMessage(
                    v6,
                    2,
                    (int)SclEvent_Generic_Warning,
                    1658,
                    (__int64)"SclRegProcessUserProfileHives",
                    "Required profile hive does not exist: [%ws].",
                    v21);
                }
                else
                {
                  SclLogGenericMessage(
                    v6,
                    1,
                    (int)SclEvent_Generic_Info,
                    1665,
                    (__int64)"SclRegProcessUserProfileHives",
                    "Optional profile hive does not exist, skipping: [%ws].",
                    v21);
                }
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
              }
            }
            ++v20;
          }
          while ( String >= 0 );
          i = v25;
        }
      }
    }
    else
    {
      SclLogGenericMessage(
        v6,
        3,
        (int)SclEvent_Generic_Error,
        1576,
        (__int64)"SclRegProcessUserProfileHives",
        "(%lx): Failure during enumeration of subkeys.",
        v15);
    }
    if ( Handle )
      NtClose(Handle);
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  if ( v28 )
    NtClose(v28);
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x18000bc68  push    rbp
0x18000bc6a  push    rbx
0x18000bc6b  push    rsi
0x18000bc6c  push    rdi
0x18000bc6d  push    r12
0x18000bc6f  push    r13
0x18000bc71  push    r14
0x18000bc73  push    r15
0x18000bc75  lea     rbp, [rsp-0C18h]
0x18000bc7d  sub     rsp, 0D18h
0x18000bc84  mov     rax, cs:__security_cookie
0x18000bc8b  xor     rax, rsp
0x18000bc8e  mov     [rbp+0C50h+var_50], rax
0x18000bc95  mov     r12, [rbp+0C50h+arg_20]
0x18000bc9c  lea     r13, [rcx+480h]
0x18000bca3  mov     [rbp+0C50h+var_CC0], r12
0x18000bca7  lea     rax, aOperatingOnUse; "Operating on user-specific profile hive"...
0x18000bcae  mov     r12, [rbp+0C50h+arg_28]
0x18000bcb5  lea     r15, aSclregprocessu_0; "SclRegProcessUserProfileHives"
0x18000bcbc  mov     r14, r9
0x18000bcbf  mov     [rbp+0C50h+var_CD0], rcx
0x18000bcc3  mov     rbx, r8
0x18000bcc6  mov     [rsp+0D50h+var_D28], rax
0x18000bccb  mov     rsi, rdx
0x18000bcce  mov     [rbp+0C50h+var_CC8], r12
0x18000bcd2  xor     r12d, r12d
0x18000bcd5  mov     [rsp+0D50h+var_D30], r15
0x18000bcda  test    rcx, rcx
0x18000bcdd  mov     [rsp+0D50h+var_D10], r12b
0x18000bce2  mov     r9d, 5D0h
0x18000bce8  mov     [rsp+0D50h+var_CF8], r12
0x18000bced  cmovz   r13, r12
0x18000bcf1  mov     [rsp+0D50h+KeyHandle], r12
0x18000bcf6  mov     rcx, r13
0x18000bcf9  mov     [rsp+0D50h+var_CD8], r12
0x18000bcfe  lea     r8, SclEvent_Generic_Info
0x18000bd05  lea     edx, [r12+1]
0x18000bd0a  call    SclLogGenericMessage
0x18000bd0f  mov     rcx, gs:60h
0x18000bd18  mov     r8d, 810h; Size
0x18000bd1e  xor     edx, edx; Flags
0x18000bd20  mov     [rsp+0D50h+var_D00], r8d
0x18000bd25  mov     rcx, [rcx+30h]; HeapHandle
0x18000bd29  call    cs:__imp_RtlAllocateHeap
0x18000bd2f  mov     [rsp+0D50h+var_CE8], rax
0x18000bd34  mov     rdi, rax
0x18000bd37  test    rax, rax
0x18000bd3a  jnz     short loc_18000BD54
0x18000bd3c  mov     ebx, 0C0000017h
0x18000bd41  lea     rax, aLxCouldNotAllo; "(%lx): Could not allocate memory."
0x18000bd48  mov     dword ptr [rsp+0D50h+var_D20], ebx
0x18000bd4c  mov     r9d, 5DAh
0x18000bd52  jmp     short loc_18000BD81
0x18000bd54  lea     r9, [rsp+0D50h+var_CF8]
0x18000bd59  mov     r8d, 0F003Fh
0x18000bd5f  mov     rdx, rbx
0x18000bd62  mov     rcx, rsi
0x18000bd65  call    SclCreateKey
0x18000bd6a  mov     ebx, eax
0x18000bd6c  test    eax, eax
0x18000bd6e  jns     short loc_18000BDA4
0x18000bd70  mov     dword ptr [rsp+0D50h+var_D20], eax
0x18000bd74  mov     r9d, 5E4h
0x18000bd7a  lea     rax, aLxFailedToOpen_4; "(%lx): Failed to open PROFILELIST key."
0x18000bd81  mov     [rsp+0D50h+var_D28], rax
0x18000bd86  lea     r8, SclEvent_Generic_Error
0x18000bd8d  mov     edx, 3
0x18000bd92  mov     [rsp+0D50h+var_D30], r15
0x18000bd97  mov     rcx, r13
0x18000bd9a  call    SclLogGenericMessage
0x18000bd9f  jmp     loc_18000BE59
0x18000bda4  lea     r9, [rsp+0D50h+KeyHandle]
0x18000bda9  mov     r8d, 0F003Fh
0x18000bdaf  mov     rdx, r14
0x18000bdb2  mov     rcx, rsi
0x18000bdb5  call    SclCreateKey
0x18000bdba  mov     ebx, eax
0x18000bdbc  test    eax, eax
0x18000bdbe  js      loc_18000BE59
0x18000bdc4  mov     rcx, [rsp+0D50h+KeyHandle]; KeyHandle
0x18000bdc9  lea     r8, [rsp+0D50h+var_D10]
0x18000bdce  lea     rdx, aPathname; "PATHNAME"
0x18000bdd5  call    SclRegValueExists
0x18000bdda  mov     ebx, eax
0x18000bddc  test    eax, eax
0x18000bdde  js      short loc_18000BE59
0x18000bde0  cmp     [rsp+0D50h+var_D10], r12b
0x18000bde5  jz      short loc_18000BE59
0x18000bde7  mov     rcx, [rsp+0D50h+KeyHandle]
0x18000bdec  lea     r9, [rbp+0C50h+var_670]
0x18000bdf3  lea     r8, aPathname; "PATHNAME"
0x18000bdfa  mov     dword ptr [rsp+0D50h+var_D30], 30Ch
0x18000be02  xor     edx, edx
0x18000be04  call    SclRegGetString
0x18000be09  mov     ebx, eax
0x18000be0b  test    eax, eax
0x18000be0d  js      short loc_18000BE59
0x18000be0f  movzx   ecx, [rbp+0C50h+var_670]
0x18000be16  lea     eax, [rcx-61h]
0x18000be19  cmp     ax, 19h
0x18000be1d  jbe     short loc_18000BE29
0x18000be1f  sub     cx, 41h ; 'A'
0x18000be23  cmp     cx, 19h
0x18000be27  ja      short loc_18000BE59
0x18000be29  mov     eax, 3Ah ; ':'
0x18000be2e  cmp     ax, [rbp+0C50h+var_66E]
0x18000be35  jnz     short loc_18000BE59
0x18000be37  mov     eax, 5Ch ; '\'
0x18000be3c  cmp     ax, [rbp+0C50h+var_66C]
0x18000be43  jnz     short loc_18000BE59
0x18000be45  lea     r14, [rbp+0C50h+var_670]
0x18000be4c  mov     [rbp+0C50h+var_66A], r12w
0x18000be54  mov     [rsp+0D50h+var_CD8], r14
0x18000be59  mov     esi, r12d
0x18000be5c  mov     [rsp+0D50h+var_D0C], esi
0x18000be60  test    ebx, ebx
0x18000be62  js      loc_18000C1B2
0x18000be68  mov     rcx, [rsp+0D50h+var_CF8]
0x18000be6d  lea     rax, [rsp+0D50h+P]
0x18000be72  mov     [rsp+0D50h+var_D20], rax
0x18000be77  lea     r9, [rsp+0D50h+var_CE8]
0x18000be7c  lea     rax, [rsp+0D50h+var_D00]
0x18000be81  mov     dword ptr [rsp+0D50h+var_D28], 2
0x18000be89  mov     edx, esi
0x18000be8b  mov     [rsp+0D50h+var_D30], rax
0x18000be90  mov     dword ptr [rsp+0D50h+P], r12d
0x18000be95  mov     [rsp+0D50h+Handle], r12
0x18000be9a  call    SclRegEnumerateKey
0x18000be9f  mov     ebx, eax
0x18000bea1  cmp     eax, 8000001Ah
0x18000bea6  jz      loc_18000C0BF
0x18000beac  mov     rdi, [rsp+0D50h+var_CE8]
0x18000beb1  test    eax, eax
0x18000beb3  jns     short loc_18000BEE9
0x18000beb5  mov     dword ptr [rsp+0D50h+var_D20], eax
0x18000beb9  lea     r8, SclEvent_Generic_Error
0x18000bec0  lea     rax, aLxFailureDurin; "(%lx): Failure during enumeration of su"...
0x18000bec7  mov     r9d, 628h
0x18000becd  mov     [rsp+0D50h+var_D28], rax
0x18000bed2  mov     edx, 3
0x18000bed7  mov     rcx, r13
0x18000beda  mov     [rsp+0D50h+var_D30], r15
0x18000bedf  call    SclLogGenericMessage
0x18000bee4  jmp     loc_18000C0A1
0x18000bee9  mov     edx, [rdi+0Ch]
0x18000beec  mov     eax, [rsp+0D50h+var_D00]
0x18000bef0  lea     ecx, [rdx+10h]
0x18000bef3  add     rcx, 2
0x18000bef7  cmp     rcx, rax
0x18000befa  ja      loc_18000C0B8
0x18000bf00  mov     ecx, edx
0x18000bf02  lea     r9, [rsp+0D50h+Handle]
0x18000bf07  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000bf0b  lea     rdx, [rdi+10h]
0x18000bf0f  mov     r8d, 0F003Fh
0x18000bf15  mov     [rcx+rdi+10h], r12w
0x18000bf1b  mov     rcx, [rsp+0D50h+var_CF8]
0x18000bf20  call    SclCreateKey
0x18000bf25  mov     ebx, eax
0x18000bf27  test    eax, eax
0x18000bf29  js      loc_18000C0A1
0x18000bf2f  mov     rcx, [rsp+0D50h+Handle]
0x18000bf34  lea     r9, [rbp+0C50h+var_C90]
0x18000bf38  lea     r8, aProfileimagepa; "PROFILEIMAGEPATH"
0x18000bf3f  mov     dword ptr [rsp+0D50h+var_D30], 30Ch
0x18000bf47  xor     edx, edx
0x18000bf49  call    SclRegGetString
0x18000bf4e  test    eax, eax
0x18000bf50  js      loc_18000C0A1
0x18000bf56  lea     rax, [rbp+0C50h+var_C90]
0x18000bf5a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000bf5e  inc     r14
0x18000bf61  cmp     [rax+r14*2], r12w
0x18000bf66  jnz     short loc_18000BF5E
0x18000bf68  lea     rax, aNtuserDat; "\\NTUSER.DAT"
0x18000bf6f  mov     [rbp+0C50h+var_CB0], 1
0x18000bf73  mov     [rbp+0C50h+var_CB8], rax
0x18000bf77  mov     r15d, r12d
0x18000bf7a  lea     rax, aAppdataLocalMi; "\\AppData\\Local\\Microsoft\\Windows\\U"...
0x18000bf81  mov     [rbp+0C50h+var_CA0], r12b
0x18000bf85  mov     [rbp+0C50h+var_CA8], rax
0x18000bf89  cmp     r15d, 2
0x18000bf8d  jnb     loc_18000C096
0x18000bf93  mov     [rsp+0D50h+P], r12
0x18000bf98  lea     rcx, [rbp+0C50h+var_C90]
0x18000bf9c  mov     r12d, r15d
0x18000bf9f  lea     rcx, [rcx+r14*2]
0x18000bfa3  add     r12, r12
0x18000bfa6  mov     edx, 30Ch
0x18000bfab  sub     rdx, r14
0x18000bfae  mov     r8, [rbp+r12*8+0C50h+var_CB8]
0x18000bfb3  call    RtlStringCchCopyW
0x18000bfb8  mov     ebx, eax
0x18000bfba  test    eax, eax
0x18000bfbc  js      loc_18000C088
0x18000bfc2  mov     r9, [rbp+0C50h+var_CC8]
0x18000bfc6  lea     rax, [rsp+0D50h+P]
0x18000bfcb  mov     r8, [rbp+0C50h+var_CC0]
0x18000bfcf  lea     rdx, [rbp+0C50h+var_C90]
0x18000bfd3  mov     rcx, [rbp+0C50h+var_CD0]
0x18000bfd7  mov     [rsp+0D50h+var_D28], rax
0x18000bfdc  mov     rax, [rsp+0D50h+var_CD8]
0x18000bfe1  mov     [rsp+0D50h+var_D30], rax
0x18000bfe6  call    SclpRegExpandProfileHivePath
0x18000bfeb  mov     ebx, eax
0x18000bfed  test    eax, eax
0x18000bfef  js      loc_18000C088
0x18000bff5  mov     rsi, [rsp+0D50h+P]
0x18000bffa  mov     rcx, rsi
0x18000bffd  call    SclFileObjectExists
0x18000c002  test    al, al
0x18000c004  jz      short loc_18000C016
0x18000c006  mov     rcx, [rbp+0C50h+var_CD0]
0x18000c00a  mov     rdx, rsi
0x18000c00d  call    SclRegProcessProfileHive
0x18000c012  mov     ebx, eax
0x18000c014  jmp     short loc_18000C070
0x18000c016  cmp     [rbp+r12*8+0C50h+var_CB0], 0
0x18000c01c  mov     rcx, r13
0x18000c01f  mov     [rsp+0D50h+var_D20], rsi
0x18000c024  jz      short loc_18000C041
0x18000c026  lea     rax, aRequiredProfil; "Required profile hive does not exist: ["...
0x18000c02d  mov     r9d, 67Ah
0x18000c033  lea     r8, SclEvent_Generic_Warning
0x18000c03a  mov     edx, 2
0x18000c03f  jmp     short loc_18000C05A
0x18000c041  lea     rax, aOptionalProfil; "Optional profile hive does not exist, s"...
0x18000c048  mov     r9d, 681h
0x18000c04e  lea     r8, SclEvent_Generic_Info
0x18000c055  mov     edx, 1
0x18000c05a  mov     [rsp+0D50h+var_D28], rax
0x18000c05f  lea     rax, aSclregprocessu_0; "SclRegProcessUserProfileHives"
0x18000c066  mov     [rsp+0D50h+var_D30], rax
0x18000c06b  call    SclLogGenericMessage
0x18000c070  mov     rcx, gs:60h
0x18000c079  mov     r8, rsi; P
0x18000c07c  xor     edx, edx; Flags
0x18000c07e  mov     rcx, [rcx+30h]; HeapHandle
0x18000c082  call    cs:__imp_RtlFreeHeap
0x18000c088  inc     r15d
0x18000c08b  xor     r12d, r12d
0x18000c08e  test    ebx, ebx
0x18000c090  jns     loc_18000BF89
0x18000c096  mov     esi, [rsp+0D50h+var_D0C]
0x18000c09a  lea     r15, aSclregprocessu_0; "SclRegProcessUserProfileHives"
0x18000c0a1  mov     rcx, [rsp+0D50h+Handle]; Handle
0x18000c0a6  test    rcx, rcx
0x18000c0a9  jz      short loc_18000C0B1
0x18000c0ab  call    cs:__imp_NtClose
0x18000c0b1  inc     esi
0x18000c0b3  jmp     loc_18000BE5C
0x18000c0b8  mov     ebx, 80000005h
0x18000c0bd  jmp     short loc_18000C0A1
0x18000c0bf  mov     rcx, [rsp+0D50h+var_CF8]
0x18000c0c4  lea     r9, [rbp+0C50h+var_C90]
0x18000c0c8  lea     r8, aDefault; "Default"
0x18000c0cf  mov     [rsp+0D50h+Handle], r12
0x18000c0d4  xor     edx, edx
0x18000c0d6  mov     dword ptr [rsp+0D50h+var_D30], 30Ch
0x18000c0de  call    SclRegGetString
0x18000c0e3  mov     ebx, eax
0x18000c0e5  test    eax, eax
0x18000c0e7  js      loc_18000C1AD
0x18000c0ed  lea     r8, aNtuserDat; "\\NTUSER.DAT"
0x18000c0f4  mov     edx, 30Ch
0x18000c0f9  lea     rcx, [rbp+0C50h+var_C90]
0x18000c0fd  call    RtlStringCchCatW
0x18000c102  mov     ebx, eax
0x18000c104  test    eax, eax
0x18000c106  js      loc_18000C1AD
0x18000c10c  mov     r15, [rbp+0C50h+var_CD0]
0x18000c110  lea     rax, [rsp+0D50h+Handle]
0x18000c115  mov     r9, [rbp+0C50h+var_CC8]
0x18000c119  lea     rdx, [rbp+0C50h+var_C90]
0x18000c11d  mov     r8, [rbp+0C50h+var_CC0]
0x18000c121  mov     rcx, r15
0x18000c124  mov     [rsp+0D50h+var_D28], rax
0x18000c129  mov     rax, [rsp+0D50h+var_CD8]
0x18000c12e  mov     [rsp+0D50h+var_D30], rax
0x18000c133  call    SclpRegExpandProfileHivePath
0x18000c138  mov     ebx, eax
0x18000c13a  test    eax, eax
0x18000c13c  js      short loc_18000C1AD
0x18000c13e  mov     rdi, [rsp+0D50h+Handle]
0x18000c143  mov     rcx, rdi
0x18000c146  call    SclFileObjectExists
0x18000c14b  test    al, al
0x18000c14d  jz      short loc_18000C15E
0x18000c14f  mov     rdx, rdi
0x18000c152  mov     rcx, r15
0x18000c155  call    SclRegProcessProfileHive
0x18000c15a  mov     ebx, eax
0x18000c15c  jmp     short loc_18000C195
0x18000c15e  lea     rax, aDefaultUserPro; "Default user profile hive does not exis"...
0x18000c165  mov     [rsp+0D50h+var_D20], rdi
0x18000c16a  mov     [rsp+0D50h+var_D28], rax
0x18000c16f  lea     r8, SclEvent_Generic_Error
0x18000c176  lea     rax, aSclregprocessu_0; "SclRegProcessUserProfileHives"
0x18000c17d  mov     r9d, 6BFh
0x18000c183  mov     edx, 3
  ... truncated ...
```
