# FreeUserStructure(_USER_ALL_INFORMATION *,int)

- ea: `0x180007300`
- end: `0x18000759e`
- name: `?FreeUserStructure@@YAJPEAU_USER_ALL_INFORMATION@@H@Z`
- size: `670`
- prototype: `__int64 __fastcall(struct _USER_ALL_INFORMATION *pv, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800020d0`
- `0x180002670`
- `0x180005e60`
- `0x180014d90`

## callees

- `0x180007300`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000732d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000734b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000739f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800073c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800073e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000751c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000756b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000758b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000732d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000734b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007367`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007383`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000739f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800073c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800073e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007411`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007439`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800074f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000751c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007543`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000756b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000758b`

## pseudocode

```c
__int64 __fastcall FreeUserStructure(struct _USER_ALL_INFORMATION *pv, int a2)
{
  PWSTR Buffer; // rcx
  PWSTR v5; // rcx
  PWSTR v6; // rcx
  PWSTR v7; // rcx
  PWSTR v8; // rcx
  PWSTR v9; // rcx
  PWSTR v10; // rcx
  PWSTR v11; // rcx
  PWSTR v12; // rcx
  PWSTR v13; // rcx
  __int64 MaximumLength; // rcx
  PWSTR v15; // rax
  __int64 v16; // rcx
  PWSTR v17; // rax
  PWSTR v18; // rcx
  PUCHAR SecurityDescriptor; // rcx
  PUCHAR LogonHours; // rcx

  if ( pv )
  {
    if ( pv->UserName.MaximumLength )
    {
      Buffer = pv->UserName.Buffer;
      if ( Buffer )
        CoTaskMemFree(Buffer);
    }
    *(_DWORD *)&pv->UserName.Length = 0;
    pv->UserName.Buffer = 0;
    if ( pv->FullName.MaximumLength )
    {
      v5 = pv->FullName.Buffer;
      if ( v5 )
        CoTaskMemFree(v5);
    }
    *(_DWORD *)&pv->FullName.Length = 0;
    pv->FullName.Buffer = 0;
    if ( pv->HomeDirectory.MaximumLength )
    {
      v6 = pv->HomeDirectory.Buffer;
      if ( v6 )
        CoTaskMemFree(v6);
    }
    *(_DWORD *)&pv->HomeDirectory.Length = 0;
    pv->HomeDirectory.Buffer = 0;
    if ( pv->HomeDirectoryDrive.MaximumLength )
    {
      v7 = pv->HomeDirectoryDrive.Buffer;
      if ( v7 )
        CoTaskMemFree(v7);
    }
    *(_DWORD *)&pv->HomeDirectoryDrive.Length = 0;
    pv->HomeDirectoryDrive.Buffer = 0;
    if ( pv->ScriptPath.MaximumLength )
    {
      v8 = pv->ScriptPath.Buffer;
      if ( v8 )
        CoTaskMemFree(v8);
    }
    *(_DWORD *)&pv->ScriptPath.Length = 0;
    pv->ScriptPath.Buffer = 0;
    if ( pv->ProfilePath.MaximumLength )
    {
      v9 = pv->ProfilePath.Buffer;
      if ( v9 )
        CoTaskMemFree(v9);
    }
    *(_DWORD *)&pv->ProfilePath.Length = 0;
    pv->ProfilePath.Buffer = 0;
    if ( pv->AdminComment.MaximumLength )
    {
      v10 = pv->AdminComment.Buffer;
      if ( v10 )
        CoTaskMemFree(v10);
    }
    *(_DWORD *)&pv->AdminComment.Length = 0;
    pv->AdminComment.Buffer = 0;
    if ( pv->WorkStations.MaximumLength )
    {
      v11 = pv->WorkStations.Buffer;
      if ( v11 )
        CoTaskMemFree(v11);
    }
    *(_DWORD *)&pv->WorkStations.Length = 0;
    pv->WorkStations.Buffer = 0;
    if ( pv->UserComment.MaximumLength )
    {
      v12 = pv->UserComment.Buffer;
      if ( v12 )
        CoTaskMemFree(v12);
    }
    *(_DWORD *)&pv->UserComment.Length = 0;
    pv->UserComment.Buffer = 0;
    if ( pv->Parameters.MaximumLength )
    {
      v13 = pv->Parameters.Buffer;
      if ( v13 )
        CoTaskMemFree(v13);
    }
    MaximumLength = pv->LmPassword.MaximumLength;
    *(_DWORD *)&pv->Parameters.Length = 0;
    pv->Parameters.Buffer = 0;
    if ( (_WORD)MaximumLength )
    {
      v15 = pv->LmPassword.Buffer;
      if ( v15 )
      {
        do
        {
          *(_BYTE *)v15 = 0;
          v15 = (PWSTR)((char *)v15 + 1);
          --MaximumLength;
        }
        while ( MaximumLength );
        CoTaskMemFree(pv->LmPassword.Buffer);
      }
    }
    v16 = pv->NtPassword.MaximumLength;
    *(_DWORD *)&pv->LmPassword.Length = 0;
    pv->LmPassword.Buffer = 0;
    if ( (_WORD)v16 )
    {
      v17 = pv->NtPassword.Buffer;
      if ( v17 )
      {
        do
        {
          *(_BYTE *)v17 = 0;
          v17 = (PWSTR)((char *)v17 + 1);
          --v16;
        }
        while ( v16 );
        CoTaskMemFree(pv->NtPassword.Buffer);
      }
    }
    *(_DWORD *)&pv->NtPassword.Length = 0;
    pv->NtPassword.Buffer = 0;
    if ( pv->PrivateData.MaximumLength )
    {
      v18 = pv->PrivateData.Buffer;
      if ( v18 )
        CoTaskMemFree(v18);
    }
    *(_DWORD *)&pv->PrivateData.Length = 0;
    pv->PrivateData.Buffer = 0;
    if ( pv->SecurityDescriptor.Length )
    {
      SecurityDescriptor = pv->SecurityDescriptor.SecurityDescriptor;
      if ( SecurityDescriptor )
        CoTaskMemFree(SecurityDescriptor);
    }
    pv->SecurityDescriptor.Length = 0;
    pv->SecurityDescriptor.SecurityDescriptor = 0;
    if ( pv->LogonHours.UnitsPerWeek )
    {
      LogonHours = pv->LogonHours.LogonHours;
      if ( LogonHours )
        CoTaskMemFree(LogonHours);
    }
    pv->LogonHours.UnitsPerWeek = 0;
    pv->LogonHours.LogonHours = 0;
    if ( a2 )
      CoTaskMemFree(pv);
  }
  return 0;
}

```

## disassembly

```asm
0x180007300  mov     [rsp+arg_8], rbx
0x180007305  push    rdi
0x180007306  sub     rsp, 20h
0x18000730a  mov     edi, edx
0x18000730c  mov     rbx, rcx
0x18000730f  test    rcx, rcx
0x180007312  jz      loc_180007591
0x180007318  cmp     word ptr [rcx+32h], 0
0x18000731d  mov     [rsp+28h+arg_0], rsi
0x180007322  jbe     short loc_180007333
0x180007324  mov     rcx, [rcx+38h]; pv
0x180007328  test    rcx, rcx
0x18000732b  jz      short loc_180007333
0x18000732d  call    cs:__imp_CoTaskMemFree
0x180007333  xor     esi, esi
0x180007335  mov     [rbx+30h], esi
0x180007338  mov     [rbx+38h], rsi
0x18000733c  cmp     [rbx+42h], si
0x180007340  jbe     short loc_180007351
0x180007342  mov     rcx, [rbx+48h]; pv
0x180007346  test    rcx, rcx
0x180007349  jz      short loc_180007351
0x18000734b  call    cs:__imp_CoTaskMemFree
0x180007351  mov     [rbx+40h], esi
0x180007354  mov     [rbx+48h], rsi
0x180007358  cmp     [rbx+52h], si
0x18000735c  jbe     short loc_18000736D
0x18000735e  mov     rcx, [rbx+58h]; pv
0x180007362  test    rcx, rcx
0x180007365  jz      short loc_18000736D
0x180007367  call    cs:__imp_CoTaskMemFree
0x18000736d  mov     [rbx+50h], esi
0x180007370  mov     [rbx+58h], rsi
0x180007374  cmp     [rbx+62h], si
0x180007378  jbe     short loc_180007389
0x18000737a  mov     rcx, [rbx+68h]; pv
0x18000737e  test    rcx, rcx
0x180007381  jz      short loc_180007389
0x180007383  call    cs:__imp_CoTaskMemFree
0x180007389  mov     [rbx+60h], esi
0x18000738c  mov     [rbx+68h], rsi
0x180007390  cmp     [rbx+72h], si
0x180007394  jbe     short loc_1800073A5
0x180007396  mov     rcx, [rbx+78h]; pv
0x18000739a  test    rcx, rcx
0x18000739d  jz      short loc_1800073A5
0x18000739f  call    cs:__imp_CoTaskMemFree
0x1800073a5  mov     [rbx+70h], esi
0x1800073a8  mov     [rbx+78h], rsi
0x1800073ac  cmp     [rbx+82h], si
0x1800073b3  jbe     short loc_1800073C7
0x1800073b5  mov     rcx, [rbx+88h]; pv
0x1800073bc  test    rcx, rcx
0x1800073bf  jz      short loc_1800073C7
0x1800073c1  call    cs:__imp_CoTaskMemFree
0x1800073c7  mov     [rbx+80h], esi
0x1800073cd  mov     [rbx+88h], rsi
0x1800073d4  cmp     [rbx+92h], si
0x1800073db  jbe     short loc_1800073EF
0x1800073dd  mov     rcx, [rbx+98h]; pv
0x1800073e4  test    rcx, rcx
0x1800073e7  jz      short loc_1800073EF
0x1800073e9  call    cs:__imp_CoTaskMemFree
0x1800073ef  mov     [rbx+90h], esi
0x1800073f5  mov     [rbx+98h], rsi
0x1800073fc  cmp     [rbx+0A2h], si
0x180007403  jbe     short loc_180007417
0x180007405  mov     rcx, [rbx+0A8h]; pv
0x18000740c  test    rcx, rcx
0x18000740f  jz      short loc_180007417
0x180007411  call    cs:__imp_CoTaskMemFree
0x180007417  mov     [rbx+0A0h], esi
0x18000741d  mov     [rbx+0A8h], rsi
0x180007424  cmp     [rbx+0B2h], si
0x18000742b  jbe     short loc_18000743F
0x18000742d  mov     rcx, [rbx+0B8h]; pv
0x180007434  test    rcx, rcx
0x180007437  jz      short loc_18000743F
0x180007439  call    cs:__imp_CoTaskMemFree
0x18000743f  mov     [rbx+0B0h], esi
0x180007445  mov     [rbx+0B8h], rsi
0x18000744c  cmp     [rbx+0C2h], si
0x180007453  jbe     short loc_180007467
0x180007455  mov     rcx, [rbx+0C8h]; pv
0x18000745c  test    rcx, rcx
0x18000745f  jz      short loc_180007467
0x180007461  call    cs:__imp_CoTaskMemFree
0x180007467  movzx   ecx, word ptr [rbx+0D2h]
0x18000746e  mov     [rbx+0C0h], esi
0x180007474  mov     [rbx+0C8h], rsi
0x18000747b  test    cx, cx
0x18000747e  jz      short loc_1800074AB
0x180007480  mov     rax, [rbx+0D8h]
0x180007487  test    rax, rax
0x18000748a  jz      short loc_1800074AB
0x18000748c  test    rcx, rcx
0x18000748f  jz      short loc_18000749E
0x180007491  mov     [rax], sil
0x180007494  lea     rax, [rax+1]
0x180007498  sub     rcx, 1
0x18000749c  jnz     short loc_180007491
0x18000749e  mov     rcx, [rbx+0D8h]; pv
0x1800074a5  call    cs:__imp_CoTaskMemFree
0x1800074ab  movzx   ecx, word ptr [rbx+0E2h]
0x1800074b2  mov     [rbx+0D0h], esi
0x1800074b8  mov     [rbx+0D8h], rsi
0x1800074bf  test    cx, cx
0x1800074c2  jz      short loc_1800074FA
0x1800074c4  mov     rax, [rbx+0E8h]
0x1800074cb  test    rax, rax
0x1800074ce  jz      short loc_1800074FA
0x1800074d0  test    rcx, rcx
0x1800074d3  jz      short loc_1800074ED
0x1800074d5  nop     word ptr [rax+rax+00000000h]
0x1800074e0  mov     [rax], sil
0x1800074e3  lea     rax, [rax+1]
0x1800074e7  sub     rcx, 1
0x1800074eb  jnz     short loc_1800074E0
0x1800074ed  mov     rcx, [rbx+0E8h]; pv
0x1800074f4  call    cs:__imp_CoTaskMemFree
0x1800074fa  mov     [rbx+0E0h], esi
0x180007500  mov     [rbx+0E8h], rsi
0x180007507  cmp     [rbx+0F2h], si
0x18000750e  jbe     short loc_180007522
0x180007510  mov     rcx, [rbx+0F8h]; pv
0x180007517  test    rcx, rcx
0x18000751a  jz      short loc_180007522
0x18000751c  call    cs:__imp_CoTaskMemFree
0x180007522  mov     [rbx+0F0h], esi
0x180007528  mov     [rbx+0F8h], rsi
0x18000752f  cmp     [rbx+100h], esi
0x180007535  jbe     short loc_180007549
0x180007537  mov     rcx, [rbx+108h]; pv
0x18000753e  test    rcx, rcx
0x180007541  jz      short loc_180007549
0x180007543  call    cs:__imp_CoTaskMemFree
0x180007549  mov     [rbx+100h], esi
0x18000754f  mov     [rbx+108h], rsi
0x180007556  cmp     [rbx+120h], si
0x18000755d  jbe     short loc_180007571
0x18000755f  mov     rcx, [rbx+128h]; pv
0x180007566  test    rcx, rcx
0x180007569  jz      short loc_180007571
0x18000756b  call    cs:__imp_CoTaskMemFree
0x180007571  mov     [rbx+120h], si
0x180007578  mov     [rbx+128h], rsi
0x18000757f  mov     rsi, [rsp+28h+arg_0]
0x180007584  test    edi, edi
0x180007586  jz      short loc_180007591
0x180007588  mov     rcx, rbx; pv
0x18000758b  call    cs:__imp_CoTaskMemFree
0x180007591  mov     rbx, [rsp+28h+arg_8]
0x180007596  xor     eax, eax
0x180007598  add     rsp, 20h
0x18000759c  pop     rdi
0x18000759d  retn
```
