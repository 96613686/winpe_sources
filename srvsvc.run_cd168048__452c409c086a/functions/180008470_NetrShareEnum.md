# NetrShareEnum

- ea: `0x180008470`
- end: `0x18000891e`
- name: `NetrShareEnum`
- size: `1198`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008470`
- `0x180008de0`
- `0x180028c24`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800088e8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008602`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086b9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008602`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800086b9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000873b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000873b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008909`
- `ntdll!RtlInitUnicodeString` at `0x180008508`
- `ntdll!RtlInitUnicodeString` at `0x180008519`
- `ntdll!RtlInitUnicodeString` at `0x18000852b`
- `ntdll!RtlInitUnicodeString` at `0x180008636`
- `ntdll!RtlInitUnicodeString` at `0x180008643`
- `ntdll!RtlInitUnicodeString` at `0x180008508`
- `ntdll!RtlInitUnicodeString` at `0x180008519`
- `ntdll!RtlInitUnicodeString` at `0x18000852b`
- `ntdll!RtlInitUnicodeString` at `0x180008636`
- `ntdll!RtlInitUnicodeString` at `0x180008643`
- `ntdll!RtlAdjustPrivilege` at `0x180008543`
- `ntdll!RtlAdjustPrivilege` at `0x180008543`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x1800085a2`
- `ntdll!NtAccessCheckAndAuditAlarm` at `0x1800085a2`
- `RPCRT4!RpcImpersonateClient` at `0x18000854b`
- `RPCRT4!RpcImpersonateClient` at `0x18000854b`
- `RPCRT4!RpcRevertToSelf` at `0x1800085aa`
- `RPCRT4!RpcRevertToSelf` at `0x1800085aa`

## pseudocode

```c
__int64 __fastcall NetrShareEnum(PCWSTR SourceString, __int64 a2, int a3, _DWORD *a4, int *a5)
{
  unsigned int v8; // eax
  char v9; // r14
  ACCESS_MASK DesiredAccess; // edi
  struct _GENERIC_MAPPING *GenericMapping; // r15
  PSECURITY_DESCRIPTOR SecurityDescriptor; // r13
  const WCHAR *v13; // rbx
  int v14; // edx
  unsigned int v15; // ebx
  int v16; // r8d
  NTSTATUS v17; // ebx
  __int64 v18; // rdi
  unsigned int v19; // esi
  struct _UNICODE_STRING *v20; // rax
  struct _UNICODE_STRING *v21; // rbx
  int *v22; // r15
  unsigned int v23; // r13d
  int v24; // eax
  void *v25; // rbp
  bool v26; // zf
  DWORD LastError; // esi
  ULONG v28; // r14d
  void *v29; // rcx
  HLOCAL v30; // rax
  DWORD v31; // eax
  void *v32; // rcx
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned __int8 GenerateOnClose[4]; // [rsp+60h] [rbp-78h] BYREF
  int AccessStatus; // [rsp+64h] [rbp-74h] BYREF
  DWORD GrantedAccess; // [rsp+68h] [rbp-70h] BYREF
  struct _UNICODE_STRING ObjectName; // [rsp+70h] [rbp-68h] BYREF
  struct _UNICODE_STRING ObjectTypeName; // [rsp+80h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-48h] BYREF
  int OldValue; // [rsp+E8h] [rbp+10h] BYREF
  SIZE_T uBytes; // [rsp+F0h] [rbp+18h]

  LODWORD(uBytes) = a3;
  if ( !a2 )
    return 87;
  v8 = *(_DWORD *)a2;
  v9 = 0;
  if ( *(_DWORD *)a2 != 501 && v8 && (v34 = v8 - 1) != 0 )
  {
    v35 = v34 - 1;
    if ( v35 )
    {
      v36 = v35 - 500;
      if ( v36 )
      {
        if ( v36 != 1 )
          return 124;
        v9 = 1;
      }
    }
    DesiredAccess = 2;
  }
  else
  {
    DesiredAccess = 1;
  }
  GenericMapping = qword_18005C6E8;
  SecurityDescriptor = qword_18005C6F0;
  v13 = SsSharePrintSecurityObject;
  GrantedAccess = 0;
  GenerateOnClose[0] = 0;
  DestinationString = 0;
  AccessStatus = 0;
  ObjectTypeName = 0;
  LOBYTE(OldValue) = 0;
  ObjectName = 0;
  RtlInitUnicodeString(&DestinationString, L"Server");
  RtlInitUnicodeString(&ObjectTypeName, v13);
  RtlInitUnicodeString(&ObjectName, L"SRV Share Info");
  RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)&OldValue);
  v15 = RpcImpersonateClient(0);
  if ( v15 )
  {
LABEL_58:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_SLl(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v16, (_DWORD)SsSharePrintSecurityObject, DesiredAccess, v15);
    }
    return v15;
  }
  v17 = NtAccessCheckAndAuditAlarm(
          &DestinationString,
          0,
          &ObjectTypeName,
          &ObjectName,
          SecurityDescriptor,
          DesiredAccess,
          GenericMapping,
          0,
          &GrantedAccess,
          &AccessStatus,
          GenerateOnClose);
  RpcRevertToSelf();
  if ( v17 < 0 || AccessStatus )
  {
    v15 = 5;
    goto LABEL_58;
  }
  v18 = *(_QWORD *)(a2 + 8);
  if ( !v18 || *(_QWORD *)(v18 + 8) )
    return 87;
  if ( a4 )
  {
    v19 = *(_DWORD *)a2;
    if ( v19 <= 2 || v19 - 501 <= 2 || v19 == 505 || v19 == 1005 )
    {
      if ( SourceString && *SourceString == 92 && SourceString[1] == 92 )
        SourceString += 2;
      v20 = (struct _UNICODE_STRING *)LocalAlloc(0x40u, 0x60u);
      v21 = v20;
      if ( v20 )
      {
        v22 = a5;
        v23 = 0;
        *(_DWORD *)&v20[4].Length = v19;
        if ( v22 )
          v24 = *v22;
        else
          v24 = 0;
        HIDWORD(v21[5].Buffer) = v24;
        RtlInitUnicodeString(v21, 0);
        RtlInitUnicodeString(v21 + 1, SourceString);
        if ( v9 )
          LODWORD(v21[4].Buffer) = 16;
        v25 = (void *)((__int64 (__fastcall *)(_QWORD))qword_18005E540)(0);
        if ( v25 )
        {
          v26 = ((__int64)v21[4].Buffer & 1) == 0;
          LastError = 0;
          OldValue = HIDWORD(v21[5].Buffer);
          if ( v26 )
          {
            v28 = uBytes;
            if ( (unsigned int)uBytes > 0x2000 )
              v28 = 0x2000;
          }
          else
          {
            v28 = 1024;
            if ( (unsigned int)uBytes <= 0x400 )
              v28 = uBytes;
          }
          *(_QWORD *)(v18 + 8) = 0;
          while ( v23 < 5 )
          {
            v29 = *(void **)(v18 + 8);
            if ( v29 )
              LocalFree(v29);
            v30 = LocalAlloc(0x40u, v28);
            *(_QWORD *)(v18 + 8) = v30;
            if ( !v30 )
            {
              LastError = 8;
              break;
            }
            HIDWORD(v21[5].Buffer) = OldValue;
            v31 = SsServerFsControlCommon(v25, 0x146033u, v21, *(PVOID *)(v18 + 8), v28);
            LastError = v31;
            if ( v31 != 2123 && v31 != 234 || v28 >= (unsigned int)uBytes )
              break;
            v28 = uBytes;
            if ( LODWORD(v21[5].Buffer) + 1024 < (unsigned int)uBytes )
              v28 = LODWORD(v21[5].Buffer) + 1024;
            ++v23;
          }
          v32 = *(void **)(v18 + 8);
          if ( v32 && !*(_DWORD *)&v21[5].Length )
          {
            LocalFree(v32);
            *(_QWORD *)(v18 + 8) = 0;
          }
          if ( !LastError || LastError == 234 )
          {
            *(_DWORD *)v18 = *(_DWORD *)&v21[5].Length;
            *a4 = *(_DWORD *)(&v21[5].MaximumLength + 1);
            if ( *(_DWORD *)v18 )
            {
              if ( v22 )
                *v22 = HIDWORD(v21[5].Buffer);
            }
          }
          LocalFree(v21);
          ((void (__fastcall *)(void *))qword_18005E548)(v25);
        }
        else
        {
          LastError = GetLastError();
          if ( LastError == 2 )
            LastError = 2114;
          LocalFree(v21);
        }
      }
      else
      {
        return 8;
      }
    }
    else
    {
      return 124;
    }
  }
  else
  {
    return 87;
  }
  return LastError;
}

```

## disassembly

```asm
0x180008470  mov     [rsp+arg_0], rbx
0x180008475  mov     dword ptr [rsp+uBytes], r8d
0x18000847a  push    rbp
0x18000847b  push    rsi
0x18000847c  push    rdi
0x18000847d  push    r12
0x18000847f  push    r13
0x180008481  push    r14
0x180008483  push    r15
0x180008485  sub     rsp, 0A0h
0x18000848c  mov     r12, r9
0x18000848f  mov     rsi, rdx
0x180008492  mov     rbp, rcx
0x180008495  test    rdx, rdx
0x180008498  jz      loc_18000884A
0x18000849e  mov     eax, [rdx]
0x1800084a0  xor     r14b, r14b
0x1800084a3  cmp     eax, 1F5h
0x1800084a8  jnz     loc_1800087E9
0x1800084ae  mov     edi, 1
0x1800084b3  mov     r15, cs:qword_18005C6E8
0x1800084ba  lea     rdx, SourceName; "Server"
0x1800084c1  mov     r13, cs:qword_18005C6F0
0x1800084c8  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x1800084d0  mov     rbx, cs:SsSharePrintSecurityObject
0x1800084d7  xor     eax, eax
0x1800084d9  xorps   xmm0, xmm0
0x1800084dc  mov     [rsp+0D8h+var_70], eax
0x1800084e0  xorps   xmm1, xmm1
0x1800084e3  mov     [rsp+0D8h+var_78], al
0x1800084e7  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x1800084ef  mov     [rsp+0D8h+var_74], eax
0x1800084f3  movups  xmmword ptr [rsp+0D8h+ObjectTypeName.Length], xmm1
0x1800084fb  mov     byte ptr [rsp+0D8h+OldValue], 0
0x180008503  movups  xmmword ptr [rsp+0D8h+ObjectName.Length], xmm0
0x180008508  call    cs:__imp_RtlInitUnicodeString
0x18000850e  mov     rdx, rbx; SourceString
0x180008511  lea     rcx, [rsp+0D8h+ObjectTypeName]; DestinationString
0x180008519  call    cs:__imp_RtlInitUnicodeString
0x18000851f  lea     rdx, aSrvShareInfo; "SRV Share Info"
0x180008526  lea     rcx, [rsp+0D8h+ObjectName]; DestinationString
0x18000852b  call    cs:__imp_RtlInitUnicodeString
0x180008531  lea     r9, [rsp+0D8h+OldValue]; OldValue
0x180008539  xor     r8d, r8d; ForThread
0x18000853c  mov     dl, 1; NewValue
0x18000853e  mov     ecx, 15h; Privilege
0x180008543  call    cs:__imp_RtlAdjustPrivilege
0x180008549  xor     ecx, ecx; BindingHandle
0x18000854b  call    cs:__imp_RpcImpersonateClient
0x180008551  mov     ebx, eax
0x180008553  test    eax, eax
0x180008555  jnz     loc_18000885E
0x18000855b  lea     rax, [rsp+0D8h+var_78]
0x180008560  xor     edx, edx; HandleId
0x180008562  mov     [rsp+0D8h+GenerateOnClose], rax; GenerateOnClose
0x180008567  lea     r9, [rsp+0D8h+ObjectName]; ObjectName
0x18000856c  lea     rax, [rsp+0D8h+var_74]
0x180008571  mov     [rsp+0D8h+AccessStatus], rax; AccessStatus
0x180008576  lea     r8, [rsp+0D8h+ObjectTypeName]; ObjectTypeName
0x18000857e  lea     rax, [rsp+0D8h+var_70]
0x180008583  mov     [rsp+0D8h+GrantedAccess], rax; GrantedAccess
0x180008588  lea     rcx, [rsp+0D8h+DestinationString]; SubsystemName
0x180008590  mov     [rsp+0D8h+ObjectCreation], bl; ObjectCreation
0x180008594  mov     [rsp+0D8h+GenericMapping], r15; GenericMapping
0x180008599  mov     [rsp+0D8h+DesiredAccess], edi; DesiredAccess
0x18000859d  mov     [rsp+0D8h+SecurityDescriptor], r13; SecurityDescriptor
0x1800085a2  call    cs:__imp_NtAccessCheckAndAuditAlarm
0x1800085a8  mov     ebx, eax
0x1800085aa  call    cs:__imp_RpcRevertToSelf
0x1800085b0  test    ebx, ebx
0x1800085b2  js      loc_180008898
0x1800085b8  cmp     [rsp+0D8h+var_74], 0
0x1800085bd  jnz     loc_180008898
0x1800085c3  mov     rdi, [rsi+8]
0x1800085c7  test    rdi, rdi
0x1800085ca  jz      loc_18000884A
0x1800085d0  cmp     qword ptr [rdi+8], 0
0x1800085d5  jnz     loc_18000884A
0x1800085db  test    r12, r12
0x1800085de  jz      loc_180008914
0x1800085e4  mov     esi, [rsi]
0x1800085e6  cmp     esi, 2
0x1800085e9  ja      loc_1800087A5
0x1800085ef  test    rbp, rbp
0x1800085f2  jnz     loc_1800088BF
0x1800085f8  mov     edx, 60h ; '`'; uBytes
0x1800085fd  mov     ecx, 40h ; '@'; uFlags
0x180008602  call    cs:__imp_LocalAlloc
0x180008608  mov     rbx, rax
0x18000860b  test    rax, rax
0x18000860e  jz      loc_1800088DE
0x180008614  mov     r15, [rsp+0D8h+arg_20]
0x18000861c  xor     r13d, r13d
0x18000861f  mov     [rax+40h], esi
0x180008622  test    r15, r15
0x180008625  jnz     loc_1800087D6
0x18000862b  mov     eax, r13d
0x18000862e  xor     edx, edx; SourceString
0x180008630  mov     [rbx+5Ch], eax
0x180008633  mov     rcx, rbx; DestinationString
0x180008636  call    cs:__imp_RtlInitUnicodeString
0x18000863c  lea     rcx, [rbx+10h]; DestinationString
0x180008640  mov     rdx, rbp; SourceString
0x180008643  call    cs:__imp_RtlInitUnicodeString
0x180008649  test    r14b, r14b
0x18000864c  jnz     loc_18000876D
0x180008652  mov     rax, cs:qword_18005E540
0x180008659  xor     ecx, ecx
0x18000865b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008660  mov     rbp, rax
0x180008663  test    rax, rax
0x180008666  jz      loc_1800088E8
0x18000866c  test    byte ptr [rbx+48h], 1
0x180008670  mov     esi, r13d
0x180008673  mov     eax, [rbx+5Ch]
0x180008676  mov     [rsp+0D8h+OldValue], eax
0x18000867d  jz      loc_180008779
0x180008683  mov     r14d, 400h
0x180008689  cmp     dword ptr [rsp+0D8h+uBytes], r14d
0x180008691  cmovbe  r14d, dword ptr [rsp+0D8h+uBytes]
0x18000869a  mov     [rdi+8], r13
0x18000869e  cmp     r13d, 5
0x1800086a2  jnb     short loc_180008707
0x1800086a4  mov     rcx, [rdi+8]; hMem
0x1800086a8  test    rcx, rcx
0x1800086ab  jnz     loc_180008909
0x1800086b1  mov     edx, r14d; uBytes
0x1800086b4  mov     ecx, 40h ; '@'; uFlags
0x1800086b9  call    cs:__imp_LocalAlloc
0x1800086bf  mov     [rdi+8], rax
0x1800086c3  test    rax, rax
0x1800086c6  jz      loc_180008854
0x1800086cc  mov     eax, [rsp+0D8h+OldValue]
0x1800086d3  mov     r8, rbx; hMem
0x1800086d6  mov     [rbx+5Ch], eax
0x1800086d9  mov     edx, 146033h; FsControlCode
0x1800086de  mov     r9, [rdi+8]; OutputBuffer
0x1800086e2  mov     rcx, rbp; FileHandle
0x1800086e5  mov     dword ptr [rsp+0D8h+SecurityDescriptor], r14d; ULONG
0x1800086ea  call    SsServerFsControlCommon
0x1800086ef  mov     esi, eax
0x1800086f1  cmp     eax, 84Bh
0x1800086f6  jz      loc_180008810
0x1800086fc  cmp     eax, 0EAh
0x180008701  jz      loc_180008810
0x180008707  mov     rcx, [rdi+8]; hMem
0x18000870b  test    rcx, rcx
0x18000870e  jz      short loc_180008716
0x180008710  cmp     dword ptr [rbx+50h], 0
0x180008714  jz      short loc_180008792
0x180008716  test    esi, esi
0x180008718  jnz     loc_180008839
0x18000871e  mov     eax, [rbx+50h]
0x180008721  mov     [rdi], eax
0x180008723  mov     eax, [rbx+54h]
0x180008726  mov     [r12], eax
0x18000872a  cmp     dword ptr [rdi], 0
0x18000872d  jbe     short loc_180008738
0x18000872f  test    r15, r15
0x180008732  jnz     loc_1800087DE
0x180008738  mov     rcx, rbx; hMem
0x18000873b  call    cs:__imp_LocalFree
0x180008741  mov     rax, cs:qword_18005E548
0x180008748  mov     rcx, rbp
0x18000874b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008750  mov     eax, esi
0x180008752  mov     rbx, [rsp+0D8h+arg_0]
0x18000875a  add     rsp, 0A0h
0x180008761  pop     r15
0x180008763  pop     r14
0x180008765  pop     r13
0x180008767  pop     r12
0x180008769  pop     rdi
0x18000876a  pop     rsi
0x18000876b  pop     rbp
0x18000876c  retn
0x18000876d  mov     dword ptr [rbx+48h], 10h
0x180008774  jmp     loc_180008652
0x180008779  mov     r14d, dword ptr [rsp+0D8h+uBytes]
0x180008781  mov     ecx, 2000h
0x180008786  cmp     r14d, ecx
0x180008789  cmova   r14d, ecx
0x18000878d  jmp     loc_18000869A
0x180008792  call    cs:__imp_LocalFree
0x180008798  mov     qword ptr [rdi+8], 0
0x1800087a0  jmp     loc_180008716
0x1800087a5  lea     eax, [rsi-1F5h]
0x1800087ab  cmp     eax, 2
0x1800087ae  jbe     loc_1800085EF
0x1800087b4  cmp     esi, 1F9h
0x1800087ba  jz      loc_1800085EF
0x1800087c0  cmp     esi, 3EDh
0x1800087c6  jz      loc_1800085EF
0x1800087cc  mov     esi, 7Ch ; '|'
0x1800087d1  jmp     loc_180008750
0x1800087d6  mov     eax, [r15]
0x1800087d9  jmp     loc_18000862E
0x1800087de  mov     eax, [rbx+5Ch]
0x1800087e1  mov     [r15], eax
0x1800087e4  jmp     loc_180008738
0x1800087e9  test    eax, eax
0x1800087eb  jz      loc_1800084AE
0x1800087f1  sub     eax, 1
0x1800087f4  jz      loc_1800084AE
0x1800087fa  sub     eax, 1
0x1800087fd  jz      short loc_180008806
0x1800087ff  sub     eax, 1F4h
0x180008804  jnz     short loc_180008881
0x180008806  mov     edi, 2
0x18000880b  jmp     loc_1800084B3
0x180008810  mov     ecx, dword ptr [rsp+0D8h+uBytes]
0x180008817  cmp     r14d, ecx
0x18000881a  jnb     loc_180008707
0x180008820  mov     eax, [rbx+58h]
0x180008823  mov     r14d, ecx
0x180008826  add     eax, 400h
0x18000882b  cmp     eax, ecx
0x18000882d  cmovb   r14d, eax
0x180008831  inc     r13d
0x180008834  jmp     loc_18000869E
0x180008839  cmp     esi, 0EAh
0x18000883f  jz      loc_18000871E
0x180008845  jmp     loc_180008738
0x18000884a  mov     eax, 57h ; 'W'
0x18000884f  jmp     loc_180008752
0x180008854  mov     esi, 8
0x180008859  jmp     loc_180008707
0x18000885e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008865  lea     rax, WPP_GLOBAL_Control
0x18000886c  cmp     rcx, rax
0x18000886f  jz      short loc_18000887A
0x180008871  test    dword ptr [rcx+1Ch], 200h
0x180008878  jnz     short loc_18000889F
0x18000887a  mov     eax, ebx
0x18000887c  jmp     loc_180008752
0x180008881  cmp     eax, 1
0x180008884  jz      short loc_180008890
0x180008886  mov     eax, 7Ch ; '|'
0x18000888b  jmp     loc_180008752
0x180008890  mov     r14b, 1
0x180008893  jmp     loc_180008806
0x180008898  mov     ebx, 5
0x18000889d  jmp     short loc_18000885E
0x18000889f  cmp     byte ptr [rcx+19h], 1
0x1800088a3  jb      short loc_18000887A
0x1800088a5  mov     r9, cs:SsSharePrintSecurityObject
0x1800088ac  mov     rcx, [rcx+10h]
0x1800088b0  mov     [rsp+0D8h+DesiredAccess], ebx
0x1800088b4  mov     dword ptr [rsp+0D8h+SecurityDescriptor], edi
0x1800088b8  call    WPP_SF_SLl
0x1800088bd  jmp     short loc_18000887A
0x1800088bf  cmp     word ptr [rbp+0], 5Ch ; '\'
0x1800088c4  jnz     loc_1800085F8
0x1800088ca  cmp     word ptr [rbp+2], 5Ch ; '\'
0x1800088cf  jnz     loc_1800085F8
0x1800088d5  add     rbp, 4
0x1800088d9  jmp     loc_1800085F8
0x1800088de  mov     esi, 8
0x1800088e3  jmp     loc_180008750
0x1800088e8  call    cs:__imp_GetLastError
0x1800088ee  mov     esi, eax
0x1800088f0  mov     rcx, rbx; hMem
0x1800088f3  cmp     esi, 2
0x1800088f6  mov     eax, 842h
0x1800088fb  cmovz   esi, eax
0x1800088fe  call    cs:__imp_LocalFree
0x180008904  jmp     loc_180008750
0x180008909  call    cs:__imp_LocalFree
0x18000890f  jmp     loc_1800086B1
0x180008914  mov     esi, 57h ; 'W'
0x180008919  jmp     loc_180008750
```
