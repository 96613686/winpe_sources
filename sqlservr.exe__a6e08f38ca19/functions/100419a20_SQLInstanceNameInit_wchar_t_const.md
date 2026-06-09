# SQLInstanceNameInit(wchar_t const *)

- ea: `0x100419a20`
- end: `0x100419c5c`
- name: `?SQLInstanceNameInit@@YAXPEB_W@Z`
- size: `572`
- prototype: `void __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1004115f0`
- `0x100416770`

## callees

- `0x100401580`
- `0x1004198e0`
- `0x100419a20`
- `0x10044a2c0`
- `0x10044aad0`

## import_xrefs

- `KERNEL32!GetComputerNameExW` at `0x100419b72`
- `KERNEL32!GetComputerNameExW` at `0x100419b72`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100419a57`
- `instapi160!GetInstanceNameFromID` at `0x100419ad2`
- `instapi160!GetInstanceNameFromID` at `0x100419ad2`
- `instapi160!GetSQLServiceByID` at `0x100419c21`
- `instapi160!GetSQLServiceByID` at `0x100419c21`
- `instapi160!GetSvcInstanceIDFromName` at `0x100419a9a`
- `instapi160!GetSvcInstanceIDFromName` at `0x100419a9a`
- `instapi160!GetSQLServerByName` at `0x100419ba3`
- `instapi160!GetSQLServerByName` at `0x100419ba3`

## string_xrefs

- `0x100419bb6`: `GetComputerNameEx() initialization failed. Aborting Initialization`
- `0x100419bad`: `Unable to determine service name.`
- `0x100419c2b`: `Unable to obtain service name.`

## pseudocode

```c
void __fastcall SQLInstanceNameInit(const wchar_t *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax
  _WORD *v4; // rcx
  __int64 v5; // rdx
  signed __int64 v6; // rdi
  __int16 v7; // ax
  _WORD *v8; // rax
  const char *v9; // rcx
  char *v10; // rdx
  int v11; // [rsp+20h] [rbp-138h] BYREF
  DWORD nSize[3]; // [rsp+24h] [rbp-134h] BYREF
  WCHAR Buffer[136]; // [rsp+30h] [rbp-128h] BYREF

  v2 = -1;
  if ( a1 )
  {
    if ( (unsigned int)(*((_DWORD *)s_pServerConf + 3) - 1) > 1 )
      InitSharedBins();
    v3 = -1;
    do
      ++v3;
    while ( a1[v3] );
    if ( (unsigned int)v3 > 0x10 )
      FailAndExit("Error: Instance name exceeds maximum length.");
    if ( !(unsigned int)GetSvcInstanceIDFromName(a1, 0, &GlobalInstanceId) )
      FailAndExit("Error getting instance ID from name.");
    v11 = 261;
    if ( !(unsigned int)GetInstanceNameFromID(&GlobalInstanceId, (char *)qword_10049F360 + 43778, &v11) )
      FailAndExit("Error getting instance name.");
    InitRegistryEntries();
  }
  else
  {
    FailAndExit("SQL Server Instance Name not set. Aborting Initialization.");
  }
  if ( *((_DWORD *)qword_10049F360 + 3626) )
  {
    v4 = (_WORD *)((char *)qword_10049F360 + 45344);
    v5 = 261;
    v6 = (char *)a1 - ((char *)qword_10049F360 + 45344);
    do
    {
      if ( v5 == -2147483385 )
        break;
      v7 = *(_WORD *)((char *)v4 + v6);
      if ( !v7 )
        break;
      *v4++ = v7;
      --v5;
    }
    while ( v5 );
    v8 = v4 - 1;
    if ( v5 )
      v8 = v4;
    *v8 = 0;
    if ( !v5 )
    {
      v9 = "Instance name initialization failed. Aborting Initialization";
LABEL_27:
      FailAndExit(v9);
    }
  }
  else
  {
    nSize[0] = 129;
    if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
    {
      v9 = "GetComputerNameEx() initialization failed. Aborting Initialization";
      goto LABEL_27;
    }
    v11 = 261;
    if ( !(unsigned int)((__int64 (__fastcall *)(WCHAR *, char *, char *, int *))GetSQLServerByName)(
                          Buffer,
                          (char *)qword_10049F360 + 43778,
                          (char *)qword_10049F360 + 45344,
                          &v11) )
    {
      v9 = "Unable to determine service name.";
      goto LABEL_27;
    }
  }
  *((_WORD *)qword_10049F360 + 22932) = 0;
  v10 = (char *)qword_10049F360 + 45344;
  *((_QWORD *)qword_10049F360 + 1466) = (char *)qword_10049F360 + 45344;
  do
    ++v2;
  while ( *(_WORD *)&v10[2 * v2] );
  *((_DWORD *)qword_10049F360 + 2934) = 2 * v2;
  v11 = 261;
  if ( !(unsigned int)((__int64 (__fastcall *)(void *, _QWORD, char *, int *))GetSQLServiceByID)(
                        &GlobalInstanceId,
                        0,
                        (char *)qword_10049F360 + 46388,
                        &v11) )
    FailAndExit("Unable to obtain service name.");
}

```

## disassembly

```asm
0x100419a20  mov     [rsp+arg_8], rbx
0x100419a25  mov     [rsp+arg_10], rsi
0x100419a2a  push    rdi
0x100419a2b  sub     rsp, 150h
0x100419a32  mov     rax, cs:__security_cookie
0x100419a39  xor     rax, rsp
0x100419a3c  mov     [rsp+158h+var_18], rax
0x100419a44  mov     rdi, rcx
0x100419a47  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x100419a4e  test    rcx, rcx
0x100419a51  jz      loc_100419AEF
0x100419a57  mov     rax, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100419a5e  mov     rdx, [rax]
0x100419a61  mov     eax, [rdx+0Ch]
0x100419a64  dec     eax
0x100419a66  cmp     eax, 1
0x100419a69  jbe     short loc_100419A70
0x100419a6b  call    InitSharedBins
0x100419a70  mov     rax, rbx
0x100419a73  inc     rax
0x100419a76  cmp     word ptr [rdi+rax*2], 0
0x100419a7b  jnz     short loc_100419A73
0x100419a7d  cmp     eax, 10h
0x100419a80  jbe     short loc_100419A8E
0x100419a82  lea     rcx, aErrorInstanceN; "Error: Instance name exceeds maximum le"...
0x100419a89  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419a8e  lea     r8, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419a95  xor     edx, edx
0x100419a97  mov     rcx, rdi
0x100419a9a  call    cs:__imp_GetSvcInstanceIDFromName
0x100419aa0  test    eax, eax
0x100419aa2  jnz     short loc_100419AB0
0x100419aa4  lea     rcx, aErrorGettingIn_0; "Error getting instance ID from name."
0x100419aab  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419ab0  mov     rdx, cs:qword_10049F360
0x100419ab7  lea     r8, [rsp+158h+var_138]
0x100419abc  add     rdx, 0AB02h
0x100419ac3  mov     [rsp+158h+var_138], 105h
0x100419acb  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419ad2  call    cs:__imp_GetInstanceNameFromID
0x100419ad8  test    eax, eax
0x100419ada  jnz     short loc_100419AE8
0x100419adc  lea     rcx, aErrorGettingIn; "Error getting instance name."
0x100419ae3  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419ae8  call    ?InitRegistryEntries@@YAXXZ; InitRegistryEntries(void)
0x100419aed  jmp     short loc_100419AFB
0x100419aef  lea     rcx, aSqlServerInsta; "SQL Server Instance Name not set. Abort"...
0x100419af6  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419afb  mov     rax, cs:qword_10049F360
0x100419b02  xor     esi, esi
0x100419b04  cmp     [rax+38A8h], esi
0x100419b0a  jz      short loc_100419B5B
0x100419b0c  lea     rcx, [rax+0B120h]
0x100419b13  mov     edx, 105h
0x100419b18  sub     rdi, rcx
0x100419b1b  nop     dword ptr [rax+rax+00h]
0x100419b20  lea     rax, [rdx+7FFFFEF9h]
0x100419b27  test    rax, rax
0x100419b2a  jz      short loc_100419B42
0x100419b2c  movzx   eax, word ptr [rdi+rcx]
0x100419b30  test    ax, ax
0x100419b33  jz      short loc_100419B42
0x100419b35  mov     [rcx], ax
0x100419b38  add     rcx, 2
0x100419b3c  sub     rdx, 1
0x100419b40  jnz     short loc_100419B20
0x100419b42  test    rdx, rdx
0x100419b45  lea     rax, [rcx-2]
0x100419b49  cmovnz  rax, rcx
0x100419b4d  mov     [rax], si
0x100419b50  jnz     short loc_100419BC2
0x100419b52  lea     rcx, aInstanceNameIn; "Instance name initialization failed. Ab"...
0x100419b59  jmp     short loc_100419BBD
0x100419b5b  lea     r8, [rsp+158h+nSize]; nSize
0x100419b60  mov     [rsp+158h+nSize], 81h
0x100419b68  lea     rdx, [rsp+158h+Buffer]; lpBuffer
0x100419b6d  mov     ecx, 1; NameType
0x100419b72  call    cs:__imp_GetComputerNameExW
0x100419b78  test    eax, eax
0x100419b7a  jz      short loc_100419BB6
0x100419b7c  mov     rdx, cs:qword_10049F360
0x100419b83  lea     r9, [rsp+158h+var_138]
0x100419b88  lea     rcx, [rsp+158h+Buffer]
0x100419b8d  mov     [rsp+158h+var_138], 105h
0x100419b95  lea     r8, [rdx+0B120h]
0x100419b9c  add     rdx, 0AB02h
0x100419ba3  call    cs:__imp_GetSQLServerByName
0x100419ba9  test    eax, eax
0x100419bab  jnz     short loc_100419BC2
0x100419bad  lea     rcx, aUnableToDeterm; "Unable to determine service name."
0x100419bb4  jmp     short loc_100419BBD
0x100419bb6  lea     rcx, aGetcomputernam; "GetComputerNameEx() initialization fail"...
0x100419bbd  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419bc2  mov     rax, cs:qword_10049F360
0x100419bc9  mov     [rax+0B328h], si
0x100419bd0  mov     rax, cs:qword_10049F360
0x100419bd7  lea     rdx, [rax+0B120h]
0x100419bde  mov     [rax+2DD0h], rdx
0x100419be5  inc     rbx
0x100419be8  cmp     [rdx+rbx*2], si
0x100419bec  jnz     short loc_100419BE5
0x100419bee  mov     rax, cs:qword_10049F360
0x100419bf5  lea     r9, [rsp+158h+var_138]
0x100419bfa  add     ebx, ebx
0x100419bfc  lea     rcx, ?GlobalInstanceId@@3U_INST_ID@@A; _INST_ID GlobalInstanceId
0x100419c03  xor     edx, edx
0x100419c05  mov     [rax+2DD8h], ebx
0x100419c0b  mov     r8, cs:qword_10049F360
0x100419c12  add     r8, 0B534h
0x100419c19  mov     [rsp+158h+var_138], 105h
0x100419c21  call    cs:__imp_GetSQLServiceByID
0x100419c27  test    eax, eax
0x100419c29  jnz     short loc_100419C37
0x100419c2b  lea     rcx, aUnableToObtain; "Unable to obtain service name."
0x100419c32  call    ?FailAndExit@@YAXPEBD@Z; FailAndExit(char const *)
0x100419c37  mov     rcx, [rsp+158h+var_18]
0x100419c3f  xor     rcx, rsp; StackCookie
0x100419c42  call    __security_check_cookie
0x100419c47  lea     r11, [rsp+158h+var_8]
0x100419c4f  mov     rbx, [r11+18h]
0x100419c53  mov     rsi, [r11+20h]
0x100419c57  mov     rsp, r11
0x100419c5a  pop     rdi
0x100419c5b  retn
```
