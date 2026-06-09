# Sm::IsShilohClustered(char *)

- ea: `0x383ac5050`
- end: `0x383ac524e`
- name: `?IsShilohClustered@Sm@@SAHPEAD@Z`
- size: `510`
- prototype: `__int64 __fastcall(char *String2)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x38388f3d0`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x383881430`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ac5050`

## import_xrefs

- `MSVCR100!_stricmp_l` at `0x383ac50de`
- `MSVCR100!_stricmp_l` at `0x383ac50de`
- `ADVAPI32!RegOpenKeyExA` at `0x383ac513b`
- `ADVAPI32!RegOpenKeyExA` at `0x383ac513b`
- `ADVAPI32!RegCloseKey` at `0x383ac514e`
- `ADVAPI32!RegCloseKey` at `0x383ac514e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Sm::IsShilohClustered(char *String2)
{
  int v2; // eax
  int phkResult; // [rsp+20h] [rbp-1D8h]
  __int64 v5; // [rsp+30h] [rbp-1C8h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-1C0h] BYREF
  CHAR SubKey[400]; // [rsp+50h] [rbp-1A8h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v5 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48BE0[0] )
    bidScopeEnterA(&v5, off_383B48BE0[0], String2);
  memset(SubKey, 0, 388);
  SubKey[387] = 0;
  if ( _stricmp_l("MSSQLSERVER", String2, 0) )
  {
    phkResult = (int)String2;
    v2 = StringCchPrintf_lA(SubKey, 0x184u, "SOFTWARE\\Microsoft\\Microsoft SQL Server\\%s\\Cluster", 0);
  }
  else
  {
    v2 = StringCchPrintf_lA(SubKey, 0x184u, "SOFTWARE\\Microsoft\\MSSQLServer\\Cluster", 0);
  }
  if ( v2 < 0 || RegOpenKeyExA(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, hKey) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B47B68[0] )
      bidTraceA(off_383B454E8[0], 562176, off_383B47B68[0], 0, phkResult);
    if ( v5 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 0;
  }
  else
  {
    RegCloseKey(hKey[0]);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B47B70[0] )
      bidTraceA(off_383B454F0[0], 556032, off_383B47B70[0], 1, phkResult);
    if ( v5 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 1;
  }
}

```

## disassembly

```asm
0x383ac5050  push    rbx
0x383ac5052  sub     rsp, 1F0h
0x383ac5059  mov     [rsp+1F8h+var_1B8], 0FFFFFFFFFFFFFFFEh
0x383ac5062  mov     rax, cs:__security_cookie
0x383ac5069  xor     rax, rsp
0x383ac506c  mov     [rsp+1F8h+var_18], rax
0x383ac5074  mov     rbx, rcx
0x383ac5077  mov     [rsp+1F8h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x383ac5080  mov     eax, cs:_bidGblFlags
0x383ac5086  and     eax, 20004h
0x383ac508b  cmp     eax, 20004h
0x383ac5090  jnz     short loc_383AC50B2
0x383ac5092  mov     rax, cs:off_383B48BE0; "<Sm::IsShilohClustered|API|SNI> szInsta"...
0x383ac5099  test    rax, rax
0x383ac509c  jz      short loc_383AC50B2
0x383ac509e  mov     r8, rcx
0x383ac50a1  mov     rdx, cs:off_383B48BE0; "<Sm::IsShilohClustered|API|SNI> szInsta"...
0x383ac50a8  lea     rcx, [rsp+1F8h+var_1C8]
0x383ac50ad  call    _bidScopeEnterA
0x383ac50b2  mov     [rsp+1F8h+SubKey], 0
0x383ac50b7  xor     edx, edx; Val
0x383ac50b9  mov     r8d, 183h; Size
0x383ac50bf  lea     rcx, [rsp+1F8h+var_1A7]; void *
0x383ac50c4  call    memset
0x383ac50c9  mov     [rsp+1F8h+var_25], 0
0x383ac50d1  xor     r8d, r8d; Locale
0x383ac50d4  mov     rdx, rbx; String2
0x383ac50d7  lea     rcx, aMssqlserver; "MSSQLSERVER"
0x383ac50de  call    cs:__imp__stricmp_l
0x383ac50e4  xor     r9d, r9d; struct localeinfo_struct *
0x383ac50e7  mov     edx, 184h; unsigned __int64
0x383ac50ec  lea     rcx, [rsp+1F8h+SubKey]; char *
0x383ac50f1  test    eax, eax
0x383ac50f3  jnz     short loc_383AC5103
0x383ac50f5  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\MSSQLServer\\Clust"...
0x383ac50fc  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAUlocaleinfo_struct@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,localeinfo_struct *,...)
0x383ac5101  jmp     short loc_383AC5114
0x383ac5103  mov     qword ptr [rsp+1F8h+phkResult], rbx
0x383ac5108  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x383ac510f  call    ?StringCchPrintf_lA@@YAJPEAD_KPEBDPEAUlocaleinfo_struct@@ZZ; StringCchPrintf_lA(char *,unsigned __int64,char const *,localeinfo_struct *,...)
0x383ac5114  test    eax, eax
0x383ac5116  js      loc_383AC51CB
0x383ac511c  lea     rax, [rsp+1F8h+hKey]
0x383ac5121  mov     qword ptr [rsp+1F8h+phkResult], rax; phkResult
0x383ac5126  mov     r9d, 1; samDesired
0x383ac512c  xor     r8d, r8d; ulOptions
0x383ac512f  lea     rdx, [rsp+1F8h+SubKey]; lpSubKey
0x383ac5134  mov     rcx, 0FFFFFFFF80000002h; hKey
0x383ac513b  call    cs:__imp_RegOpenKeyExA
0x383ac5141  test    eax, eax
0x383ac5143  jnz     loc_383AC51CB
0x383ac5149  mov     rcx, [rsp+1F8h+hKey]; hKey
0x383ac514e  call    cs:__imp_RegCloseKey
0x383ac5154  mov     r11d, cs:_bidGblFlags
0x383ac515b  and     r11d, 20002h
0x383ac5162  cmp     r11d, 20002h
0x383ac5169  jnz     short loc_383AC5196
0x383ac516b  mov     rax, cs:off_383B47B70; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x383ac5172  test    rax, rax
0x383ac5175  jz      short loc_383AC5196
0x383ac5177  mov     r9d, 1
0x383ac517d  mov     r8, cs:off_383B47B70; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x383ac5184  mov     edx, 87C00h
0x383ac5189  mov     rcx, cs:off_383B454F0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac5190  call    _bidTraceA
0x383ac5195  nop
0x383ac5196  cmp     [rsp+1F8h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x383ac519c  jz      short loc_383AC51C4
0x383ac519e  test    byte ptr cs:_bidGblFlags, 4
0x383ac51a5  jz      short loc_383AC51C4
0x383ac51a7  mov     rcx, cs:_bidID
0x383ac51ae  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ac51b2  jz      short loc_383AC51C4
0x383ac51b4  lea     r9, [rsp+1F8h+var_1C8]
0x383ac51b9  xor     r8d, r8d
0x383ac51bc  xor     edx, edx
0x383ac51be  call    cs:off_383B15058
0x383ac51c4  mov     eax, 1
0x383ac51c9  jmp     short loc_383AC5235
0x383ac51cb  mov     eax, cs:_bidGblFlags
0x383ac51d1  and     eax, 20002h
0x383ac51d6  cmp     eax, 20002h
0x383ac51db  jnz     short loc_383AC5205
0x383ac51dd  mov     rax, cs:off_383B47B68; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x383ac51e4  test    rax, rax
0x383ac51e7  jz      short loc_383AC5205
0x383ac51e9  xor     r9d, r9d
0x383ac51ec  mov     r8, cs:off_383B47B68; "<Sm::IsShilohClustered|RET|SNI> %d{BOOL"...
0x383ac51f3  mov     edx, 89400h
0x383ac51f8  mov     rcx, cs:off_383B454E8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac51ff  call    _bidTraceA
0x383ac5204  nop
0x383ac5205  cmp     [rsp+1F8h+var_1C8], 0FFFFFFFFFFFFFFFFh
0x383ac520b  jz      short loc_383AC5233
0x383ac520d  test    byte ptr cs:_bidGblFlags, 4
0x383ac5214  jz      short loc_383AC5233
0x383ac5216  mov     rcx, cs:_bidID
0x383ac521d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ac5221  jz      short loc_383AC5233
0x383ac5223  lea     r9, [rsp+1F8h+var_1C8]
0x383ac5228  xor     r8d, r8d
0x383ac522b  xor     edx, edx
0x383ac522d  call    cs:off_383B15058
0x383ac5233  xor     eax, eax
0x383ac5235  mov     rcx, [rsp+1F8h+var_18]
0x383ac523d  xor     rcx, rsp; StackCookie
0x383ac5240  call    __security_check_cookie
0x383ac5245  add     rsp, 1F0h
0x383ac524c  pop     rbx
0x383ac524d  retn
```
