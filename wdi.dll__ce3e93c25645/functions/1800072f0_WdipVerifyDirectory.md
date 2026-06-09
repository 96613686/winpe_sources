# WdipVerifyDirectory

- ea: `0x1800072f0`
- end: `0x18000761b`
- name: `WdipVerifyDirectory`
- size: `811`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006b90`
- `0x180009570`
- `0x1800098e0`
- `0x18000bff0`

## callees

- `0x180002ba0`
- `0x1800072f0`
- `0x180008868`
- `0x1800093d0`
- `0x18000e474`
- `0x18000f1c2`
- `0x18000f1f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000744d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800074db`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180007565`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000744d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800074db`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180007565`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000756f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007457`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007470`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800074fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000756f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007588`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800073d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800073d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800075e3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000736d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000736d`

## string_xrefs

- `0x1800073ab`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x1800075cd`: `clientcore\base\diagnosis\pdi\wdi\framework\common\utils.cpp`
- `0x1800073a4`: `WdipCreateSecurityDescriptor`
- `0x1800075c6`: `WdipVerifyDirectory`

## pseudocode

```c
__int64 __fastcall WdipVerifyDirectory(__int64 a1, __int64 a2, unsigned __int16 *a3, unsigned int a4)
{
  unsigned __int64 v5; // r12
  signed int LastError; // eax
  signed int Args; // edi
  UINT SystemDirectoryW; // eax
  UINT v11; // r14d
  unsigned __int64 v12; // rax
  WCHAR *v13; // rbx
  signed int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // r14
  signed int v17; // eax
  signed int v18; // eax
  int v19; // eax
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = a4;
  memset_0(Buffer, 0, 0x208u);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SecurityAttributes.nLength = 24;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:P(D;OICI;GA;;;BG)(D;OICI;GA;;;AN)(A;OICI;GA;;;SY)(A;OICI;GA;;;BA)(A;OICI;GRGWSD;;;S-1-5-80-2970612574-785378"
           "57-698502321-558674196-1451644582)(A;OICI;GRGWSD;;;S-1-5-80-3139157870-2983391045-3678747466-658725712-1809340420)",
          1u,
          &SecurityAttributes.lpSecurityDescriptor,
          0) )
  {
    LastError = GetLastError();
    Args = LastError;
    if ( LastError > 0 )
      Args = (unsigned __int16)LastError | 0x80070000;
    if ( Args < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
        (int)L"WdipCreateSecurityDescriptor",
        332,
        (int)L"Error = %d",
        Args);
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
        (int)L"WdipVerifyDirectory",
        386,
        (int)L"Error = %d",
        Args);
      goto LABEL_29;
    }
  }
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( (unsigned __int64)SystemDirectoryW + 83 > 0x104 )
  {
    Args = -2147024882;
    goto LABEL_29;
  }
  v11 = SystemDirectoryW + 4;
  Buffer[SystemDirectoryW] = 92;
  Buffer[SystemDirectoryW + 1] = 119;
  Buffer[SystemDirectoryW + 2] = 100;
  Buffer[SystemDirectoryW + 3] = 105;
  v12 = SystemDirectoryW + 4;
  if ( v12 >= 260 )
    goto LABEL_32;
  v13 = &Buffer[v12];
  Buffer[v12] = 0;
  if ( CreateDirectoryW(Buffer, &SecurityAttributes) )
    goto LABEL_19;
  v14 = GetLastError();
  Args = v14;
  if ( v14 > 0 )
    Args = (unsigned __int16)v14 | 0x80070000;
  if ( Args >= 0 || GetLastError() == 183 )
  {
LABEL_19:
    *v13 = 92;
    Buffer[v11 + 1] = 123;
    tlx::guid_to_string_lower<unsigned short>(&Buffer[v11 + 2], a1);
    v15 = v11 + 38;
    v16 = v11 + 39;
    Buffer[v15] = 125;
    if ( (unsigned __int64)(2 * v16) >= 0x208 )
      goto LABEL_32;
    Buffer[v16] = 0;
    if ( CreateDirectoryW(Buffer, 0) )
      goto LABEL_20;
    v17 = GetLastError();
    Args = v17;
    if ( v17 > 0 )
      Args = (unsigned __int16)v17 | 0x80070000;
    if ( Args >= 0 || GetLastError() == 183 )
    {
LABEL_20:
      Buffer[v16] = 92;
      Buffer[(unsigned int)(v16 + 1)] = 123;
      tlx::guid_to_string_lower<unsigned short>(&Buffer[(unsigned int)(v16 + 2)], a2);
      Buffer[(unsigned int)(v16 + 38)] = 125;
      if ( 2 * (unsigned __int64)(unsigned int)(v16 + 39) < 0x208 )
      {
        Buffer[(unsigned int)(v16 + 39)] = 0;
        if ( CreateDirectoryW(Buffer, 0) )
          goto LABEL_26;
        v18 = GetLastError();
        Args = v18;
        if ( v18 > 0 )
          Args = (unsigned __int16)v18 | 0x80070000;
        if ( Args >= 0 || GetLastError() == 183 )
        {
LABEL_26:
          Args = 0;
          if ( a3 )
          {
            v19 = StringCchCopyW(a3, v5, Buffer);
            Args = v19;
            if ( v19 < 0 )
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\common\\utils.cpp",
                (int)L"WdipVerifyDirectory",
                472,
                (int)L"Error = %d",
                v19);
          }
        }
        goto LABEL_29;
      }
LABEL_32:
      _report_rangecheckfailure();
    }
  }
LABEL_29:
  if ( SecurityAttributes.lpSecurityDescriptor )
    LocalFree(SecurityAttributes.lpSecurityDescriptor);
  return (unsigned int)Args;
}

```

## disassembly

```asm
0x1800072f0  mov     [rsp-8+arg_0], rbx
0x1800072f5  push    rbp
0x1800072f6  push    rsi
0x1800072f7  push    rdi
0x1800072f8  push    r12
0x1800072fa  push    r13
0x1800072fc  push    r14
0x1800072fe  push    r15
0x180007300  lea     rbp, [rsp-170h]
0x180007308  sub     rsp, 270h
0x18000730f  mov     rax, cs:__security_cookie
0x180007316  xor     rax, rsp
0x180007319  mov     [rbp+1A0h+var_40], rax
0x180007320  mov     rsi, r8
0x180007323  mov     r12d, r9d
0x180007326  mov     r13, rdx
0x180007329  mov     r15, rcx
0x18000732c  xor     edx, edx; Val
0x18000732e  lea     rcx, [rsp+2A0h+Buffer]; void *
0x180007333  mov     r8d, 208h; Size
0x180007339  call    memset_0
0x18000733e  xor     eax, eax
0x180007340  lea     r8, [rsp+2A0h+SecurityAttributes.lpSecurityDescriptor]; SecurityDescriptor
0x180007345  xorps   xmm0, xmm0
0x180007348  mov     qword ptr [rsp+2A0h+SecurityAttributes.bInheritHandle], rax
0x18000734d  movups  xmmword ptr [rsp+30h], xmm0
0x180007352  xor     r9d, r9d; SecurityDescriptorSize
0x180007355  mov     [rsp+2A0h+SecurityAttributes.nLength], 18h
0x18000735d  mov     edx, 1; StringSDRevision
0x180007362  mov     [rsp+2A0h+SecurityAttributes.bInheritHandle], eax
0x180007366  lea     rcx, StringSecurityDescriptor; "D:P(D;OICI;GA;;;BG)(D;OICI;GA;;;AN)(A;O"...
0x18000736d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180007373  test    eax, eax
0x180007375  jnz     short loc_1800073C6
0x180007377  call    cs:__imp_GetLastError
0x18000737d  mov     edi, eax
0x18000737f  test    eax, eax
0x180007381  jle     short loc_18000738C
0x180007383  movzx   edi, ax
0x180007386  or      edi, 80070000h
0x18000738c  test    edi, edi
0x18000738e  jns     short loc_1800073C6
0x180007390  movzx   ebx, di
0x180007393  lea     r9, aErrorD_0; "Error = %d"
0x18000739a  mov     r8d, 14Ch; int
0x1800073a0  mov     dword ptr [rsp+2A0h+Args], ebx; Args
0x1800073a4  lea     rdx, aWdipcreatesecu; "WdipCreateSecurityDescriptor"
0x1800073ab  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800073b2  call    WdipTraceError
0x1800073b7  mov     r8d, 182h
0x1800073bd  mov     dword ptr [rsp+2A0h+Args], ebx
0x1800073c1  jmp     loc_1800075BF
0x1800073c6  mov     edx, 104h; uSize
0x1800073cb  lea     rcx, [rsp+2A0h+Buffer]; lpBuffer
0x1800073d0  call    cs:__imp_GetSystemDirectoryW
0x1800073d6  mov     edx, eax
0x1800073d8  lea     rcx, [rdx+53h]
0x1800073dc  cmp     rcx, 104h
0x1800073e3  jbe     short loc_1800073EF
0x1800073e5  mov     edi, 8007000Eh
0x1800073ea  jmp     loc_1800075D9
0x1800073ef  mov     ecx, 5Ch ; '\'
0x1800073f4  lea     r14d, [rdx+4]
0x1800073f8  mov     [rsp+rdx*2+2A0h+Buffer], cx
0x1800073fd  mov     eax, 77h ; 'w'
0x180007402  lea     ecx, [rdx+1]
0x180007405  mov     [rsp+rcx*2+2A0h+Buffer], ax
0x18000740a  lea     ecx, [rdx+2]
0x18000740d  mov     eax, 64h ; 'd'
0x180007412  mov     [rsp+rcx*2+2A0h+Buffer], ax
0x180007417  mov     eax, 69h ; 'i'
0x18000741c  lea     ecx, [rdx+3]
0x18000741f  mov     [rsp+rcx*2+2A0h+Buffer], ax
0x180007424  mov     eax, r14d
0x180007427  add     rax, rax
0x18000742a  cmp     rax, 208h
0x180007430  jnb     loc_180007615
0x180007436  lea     rbx, [rsp+2A0h+Buffer]
0x18000743b  add     rbx, rax
0x18000743e  lea     rdx, [rsp+2A0h+SecurityAttributes]; lpSecurityAttributes
0x180007443  xor     eax, eax
0x180007445  lea     rcx, [rsp+2A0h+Buffer]; lpPathName
0x18000744a  mov     [rbx], ax
0x18000744d  call    cs:__imp_CreateDirectoryW
0x180007453  test    eax, eax
0x180007455  jnz     short loc_180007481
0x180007457  call    cs:__imp_GetLastError
0x18000745d  mov     edi, eax
0x18000745f  test    eax, eax
0x180007461  jle     short loc_18000746C
0x180007463  movzx   edi, ax
0x180007466  or      edi, 80070000h
0x18000746c  test    edi, edi
0x18000746e  jns     short loc_180007481
0x180007470  call    cs:__imp_GetLastError
0x180007476  cmp     eax, 0B7h
0x18000747b  jnz     loc_1800075D9
0x180007481  lea     ecx, [r14+1]
0x180007485  mov     word ptr [rbx], 5Ch ; '\'
0x18000748a  mov     eax, 7Bh ; '{'
0x18000748f  lea     ebx, [r14+2]
0x180007493  mov     [rsp+rcx*2+2A0h+Buffer], ax
0x180007498  mov     rdx, r15
0x18000749b  lea     rcx, [rsp+2A0h+Buffer]
0x1800074a0  lea     rcx, [rcx+rbx*2]
0x1800074a4  call    ??$guid_to_string_lower@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<ushort>(ushort *,_GUID const &,bool)
0x1800074a9  lea     ebx, [rbx+24h]
0x1800074ac  mov     r15d, 7Dh ; '}'
0x1800074b2  lea     r14d, [rbx+1]
0x1800074b6  mov     [rsp+rbx*2+2A0h+Buffer], r15w
0x1800074bc  lea     rbx, [r14+r14]
0x1800074c0  cmp     rbx, 208h
0x1800074c7  jnb     loc_180007615
0x1800074cd  xor     eax, eax
0x1800074cf  lea     rcx, [rsp+2A0h+Buffer]; lpPathName
0x1800074d4  xor     edx, edx; lpSecurityAttributes
0x1800074d6  mov     [rsp+rbx+2A0h+Buffer], ax
0x1800074db  call    cs:__imp_CreateDirectoryW
0x1800074e1  test    eax, eax
0x1800074e3  jnz     short loc_18000750F
0x1800074e5  call    cs:__imp_GetLastError
0x1800074eb  mov     edi, eax
0x1800074ed  test    eax, eax
0x1800074ef  jle     short loc_1800074FA
0x1800074f1  movzx   edi, ax
0x1800074f4  or      edi, 80070000h
0x1800074fa  test    edi, edi
0x1800074fc  jns     short loc_18000750F
0x1800074fe  call    cs:__imp_GetLastError
0x180007504  cmp     eax, 0B7h
0x180007509  jnz     loc_1800075D9
0x18000750f  mov     eax, 5Ch ; '\'
0x180007514  lea     ecx, [r14+1]
0x180007518  mov     [rsp+rbx+2A0h+Buffer], ax
0x18000751d  mov     rdx, r13
0x180007520  mov     eax, 7Bh ; '{'
0x180007525  lea     ebx, [r14+2]
0x180007529  mov     [rsp+rcx*2+2A0h+Buffer], ax
0x18000752e  lea     rcx, [rsp+2A0h+Buffer]
0x180007533  lea     rcx, [rcx+rbx*2]
0x180007537  call    ??$guid_to_string_lower@G@tlx@@YAXPEAGAEBU_GUID@@_N@Z; tlx::guid_to_string_lower<ushort>(ushort *,_GUID const &,bool)
0x18000753c  lea     ecx, [rbx+24h]
0x18000753f  mov     [rsp+rcx*2+2A0h+Buffer], r15w
0x180007545  inc     ecx
0x180007547  add     rcx, rcx
0x18000754a  cmp     rcx, 208h
0x180007551  jnb     loc_180007615
0x180007557  xor     eax, eax
0x180007559  xor     edx, edx; lpSecurityAttributes
0x18000755b  mov     [rsp+rcx+2A0h+Buffer], ax
0x180007560  lea     rcx, [rsp+2A0h+Buffer]; lpPathName
0x180007565  call    cs:__imp_CreateDirectoryW
0x18000756b  test    eax, eax
0x18000756d  jnz     short loc_180007595
0x18000756f  call    cs:__imp_GetLastError
0x180007575  mov     edi, eax
0x180007577  test    eax, eax
0x180007579  jle     short loc_180007584
0x18000757b  movzx   edi, ax
0x18000757e  or      edi, 80070000h
0x180007584  test    edi, edi
0x180007586  jns     short loc_180007595
0x180007588  call    cs:__imp_GetLastError
0x18000758e  cmp     eax, 0B7h
0x180007593  jnz     short loc_1800075D9
0x180007595  xor     edi, edi
0x180007597  test    rsi, rsi
0x18000759a  jz      short loc_1800075D9
0x18000759c  mov     rdx, r12; unsigned __int64
0x18000759f  lea     r8, [rsp+2A0h+Buffer]; unsigned __int16 *
0x1800075a4  mov     rcx, rsi; unsigned __int16 *
0x1800075a7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800075ac  mov     edi, eax
0x1800075ae  test    eax, eax
0x1800075b0  jns     short loc_1800075D9
0x1800075b2  movzx   ecx, ax
0x1800075b5  mov     r8d, 1D8h; int
0x1800075bb  mov     dword ptr [rsp+2A0h+Args], ecx; Args
0x1800075bf  lea     r9, aErrorD_0; "Error = %d"
0x1800075c6  lea     rdx, aWdipverifydire; "WdipVerifyDirectory"
0x1800075cd  lea     rcx, aClientcoreBase_0; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800075d4  call    WdipTraceError
0x1800075d9  mov     rcx, [rsp+2A0h+SecurityAttributes.lpSecurityDescriptor]; hMem
0x1800075de  test    rcx, rcx
0x1800075e1  jz      short loc_1800075E9
0x1800075e3  call    cs:__imp_LocalFree
0x1800075e9  mov     eax, edi
0x1800075eb  mov     rcx, [rbp+1A0h+var_40]
0x1800075f2  xor     rcx, rsp; StackCookie
0x1800075f5  call    __security_check_cookie
0x1800075fa  mov     rbx, [rsp+2A0h+arg_0]
0x180007602  add     rsp, 270h
0x180007609  pop     r15
0x18000760b  pop     r14
0x18000760d  pop     r13
0x18000760f  pop     r12
0x180007611  pop     rdi
0x180007612  pop     rsi
0x180007613  pop     rbp
0x180007614  retn
0x180007615  call    __report_rangecheckfailure
```
