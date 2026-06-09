# JobStore::EnumStoredTasks(JobStore::TaskIndex,wmi::AutoRef<IndexEnumerator> &)

- ea: `0x180039e20`
- end: `0x18003a0be`
- name: `?EnumStoredTasks@JobStore@@QEBAJW4TaskIndex@1@AEAV?$AutoRef@VIndexEnumerator@@@wmi@@@Z`
- size: `670`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022668`
- `0x18006d418`
- `0x1800758e4`
- `0x180077e50`

## callees

- `0x18000e4c0`
- `0x180030f80`
- `0x180039e20`
- `0x18003a0c4`
- `0x18003a3c0`
- `0x180049b74`
- `0x18005223c`
- `0x180056794`
- `0x18006f04c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18003a0ab`
- `OLEAUT32!__imp_SysFreeString` at `0x18003a0ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039ebe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039f44`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039ebe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180039f44`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a082`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a099`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a082`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a099`

## string_xrefs

- `0x180039f39`: `TaskCache\Tasks`
- `0x180039f90`: `TaskCache\Tasks`
- `0x180039e84`: `TaskCache\Boot`
- `0x180039e7b`: `TaskCache\Logon`
- `0x180039e72`: `TaskCache\Plain`
- `0x180039e69`: `TaskCache\Maintenance`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall JobStore::EnumStoredTasks(__int64 a1, unsigned int a2, _QWORD *a3)
{
  const wchar_t *v6; // rdx
  LSTATUS v7; // eax
  __int64 v8; // r8
  signed int v9; // edi
  _QWORD *v10; // r10
  int v11; // edx
  const WCHAR *v12; // r9
  LSTATUS v13; // eax
  volatile signed __int32 *v14; // rax
  IndexEnumerator *v15; // rbx
  volatile signed __int32 *v17; // [rsp+30h] [rbp-10h] BYREF
  LPCWSTR lpSubKey; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+40h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+48h] BYREF

  lpSubKey = 0;
  wmi::AutoRef<JobBucket>::Release(a3);
  *a3 = 0;
  switch ( a2 )
  {
    case 1u:
      v6 = L"TaskCache\\Boot";
      break;
    case 2u:
      v6 = L"TaskCache\\Logon";
      break;
    case 3u:
      v6 = L"TaskCache\\Plain";
      break;
    case 4u:
      v6 = L"TaskCache\\Maintenance";
      break;
    default:
      goto LABEL_10;
  }
  ATL::CComBSTR::operator=(&lpSubKey, v6);
LABEL_10:
  phkResult = 0;
  hKey = 0;
  v7 = RegOpenKeyExW(*(HKEY *)(a1 + 16), lpSubKey, 0, 0x20019u, &phkResult);
  v9 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v9 = (unsigned __int16)v7 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 98;
        LODWORD(v12) = (_DWORD)lpSubKey;
LABEL_17:
        WPP_SF_Sd(v10[2], v11, (unsigned int)WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids, (_DWORD)v12, v9);
LABEL_32:
        v10 = WPP_GLOBAL_Control;
        goto LABEL_33;
      }
      goto LABEL_33;
    }
  }
  else
  {
    v13 = RegOpenKeyExW(*(HKEY *)(a1 + 16), L"TaskCache\\Tasks", 0, 0x20019u, &hKey);
    v9 = v13;
    if ( !v13 )
    {
      v14 = (volatile signed __int32 *)operator new(0x20u);
      v15 = (IndexEnumerator *)v14;
      v17 = v14;
      if ( v14 )
      {
        *(_QWORD *)v14 = &wmi::RefBase::`vftable';
        *((_DWORD *)v14 + 2) = 0;
        *(_QWORD *)v14 = &IndexEnumerator::`vftable';
        *((_DWORD *)v14 + 4) = 0;
        *((_DWORD *)v14 + 5) = -1;
        *((_QWORD *)v14 + 3) = 0;
        v17 = v14;
        _InterlockedIncrement(v14 + 2);
      }
      else
      {
        v15 = 0;
        v17 = 0;
      }
      v9 = IndexEnumerator::Initialize(v15, phkResult, hKey);
      if ( v9 >= 0 )
      {
        wmi::AutoRef<IndexEnumerator>::operator=(a3, v15);
        wmi::AutoRef<JobBucket>::Release(&v17);
      }
      else if ( v15 )
      {
        wmi::RefBase::Release(v15);
      }
      goto LABEL_32;
    }
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = 99;
        v12 = L"TaskCache\\Tasks";
        goto LABEL_17;
      }
LABEL_33:
      if ( v10 != &WPP_GLOBAL_Control
        && (*((_DWORD *)v10 + 7) & 0x40000) != 0
        && *((unsigned __int8 *)v10 + 25) >= ((v9 >> 31) & 0xFFFFFFFE) + 4 )
      {
        WPP_SF_dD(v10[2], 100, v8, a2, v9);
      }
    }
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  SysFreeString((BSTR)lpSubKey);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180039e20  push    rbp
0x180039e22  push    rbx
0x180039e23  push    rsi
0x180039e24  push    rdi
0x180039e25  push    r14
0x180039e27  mov     rbp, rsp
0x180039e2a  sub     rsp, 40h
0x180039e2e  mov     rsi, r8
0x180039e31  mov     r14d, edx
0x180039e34  mov     rbx, rcx
0x180039e37  mov     [rbp+lpSubKey], 0
0x180039e3f  mov     rcx, r8
0x180039e42  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x180039e47  mov     qword ptr [rsi], 0
0x180039e4e  mov     r9d, r14d
0x180039e51  sub     r9d, 1
0x180039e55  jz      short loc_180039E84
0x180039e57  sub     r9d, 1
0x180039e5b  jz      short loc_180039E7B
0x180039e5d  sub     r9d, 1
0x180039e61  jz      short loc_180039E72
0x180039e63  cmp     r9d, 1
0x180039e67  jnz     short loc_180039E94
0x180039e69  lea     rdx, aTaskcacheMaint; "TaskCache\\Maintenance"
0x180039e70  jmp     short loc_180039E8B
0x180039e72  lea     rdx, aTaskcachePlain; "TaskCache\\Plain"
0x180039e79  jmp     short loc_180039E8B
0x180039e7b  lea     rdx, aTaskcacheLogon; "TaskCache\\Logon"
0x180039e82  jmp     short loc_180039E8B
0x180039e84  lea     rdx, aTaskcacheBoot; "TaskCache\\Boot"
0x180039e8b  lea     rcx, [rbp+lpSubKey]
0x180039e8f  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180039e94  mov     [rbp+arg_18], 0
0x180039e9c  mov     [rbp+hKey], 0
0x180039ea4  lea     rax, [rbp+arg_18]
0x180039ea8  mov     [rsp+40h+phkResult], rax; phkResult
0x180039ead  mov     r9d, 20019h; samDesired
0x180039eb3  xor     r8d, r8d; ulOptions
0x180039eb6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180039eba  mov     rcx, [rbx+10h]; hKey
0x180039ebe  call    cs:__imp_RegOpenKeyExW
0x180039ec4  mov     edi, eax
0x180039ec6  test    eax, eax
0x180039ec8  jz      short loc_180039F27
0x180039eca  jle     short loc_180039ED5
0x180039ecc  movzx   edi, ax
0x180039ecf  or      edi, 80070000h
0x180039ed5  mov     r10, cs:WPP_GLOBAL_Control
0x180039edc  lea     rbx, WPP_GLOBAL_Control
0x180039ee3  cmp     r10, rbx
0x180039ee6  jz      loc_18003A079
0x180039eec  test    dword ptr [r10+1Ch], 40000h
0x180039ef4  jz      loc_18003A040
0x180039efa  cmp     byte ptr [r10+19h], 2
0x180039eff  jb      loc_18003A040
0x180039f05  mov     edx, 62h ; 'b'
0x180039f0a  mov     r9, [rbp+lpSubKey]
0x180039f0e  mov     dword ptr [rsp+40h+phkResult], edi
0x180039f12  lea     r8, WPP_575a7bbfdfbc316314e49eeff74208de_Traceguids
0x180039f19  mov     rcx, [r10+10h]
0x180039f1d  call    WPP_SF_Sd
0x180039f22  jmp     loc_18003A039
0x180039f27  lea     rax, [rbp+hKey]
0x180039f2b  mov     [rsp+40h+phkResult], rax; phkResult
0x180039f30  mov     r9d, 20019h; samDesired
0x180039f36  xor     r8d, r8d; ulOptions
0x180039f39  lea     rdx, SubKey; "TaskCache\\Tasks"
0x180039f40  mov     rcx, [rbx+10h]; hKey
0x180039f44  call    cs:__imp_RegOpenKeyExW
0x180039f4a  mov     edi, eax
0x180039f4c  test    eax, eax
0x180039f4e  jz      short loc_180039F9C
0x180039f50  jle     short loc_180039F5B
0x180039f52  movzx   edi, ax
0x180039f55  or      edi, 80070000h
0x180039f5b  mov     r10, cs:WPP_GLOBAL_Control
0x180039f62  lea     rbx, WPP_GLOBAL_Control
0x180039f69  cmp     r10, rbx
0x180039f6c  jz      loc_18003A079
0x180039f72  test    dword ptr [r10+1Ch], 40000h
0x180039f7a  jz      loc_18003A040
0x180039f80  cmp     byte ptr [r10+19h], 2
0x180039f85  jb      loc_18003A040
0x180039f8b  mov     edx, 63h ; 'c'
0x180039f90  lea     r9, SubKey; "TaskCache\\Tasks"
0x180039f97  jmp     loc_180039F0E
0x180039f9c  mov     ecx, 20h ; ' '; dwBytes
0x180039fa1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039fa6  mov     rbx, rax
0x180039fa9  mov     [rbp+var_10], rax
0x180039fad  test    rax, rax
0x180039fb0  jz      short loc_180039FF2
0x180039fb2  lea     rax, ??_7RefBase@wmi@@6B@; const wmi::RefBase::`vftable'
0x180039fb9  mov     [rbx], rax
0x180039fbc  mov     dword ptr [rbx+8], 0
0x180039fc3  lea     rax, ??_7IndexEnumerator@@6B@; const IndexEnumerator::`vftable'
0x180039fca  mov     [rbx], rax
0x180039fcd  mov     dword ptr [rbx+10h], 0
0x180039fd4  mov     dword ptr [rbx+14h], 0FFFFFFFFh
0x180039fdb  mov     qword ptr [rbx+18h], 0
0x180039fe3  mov     [rbp+var_10], rbx
0x180039fe7  test    rbx, rbx
0x180039fea  jz      short loc_180039FF8
0x180039fec  lock inc dword ptr [rbx+8]
0x180039ff0  jmp     short loc_180039FF8
0x180039ff2  xor     ebx, ebx
0x180039ff4  mov     [rbp+var_10], rbx
0x180039ff8  mov     r8, [rbp+hKey]; HKEY
0x180039ffc  mov     rdx, [rbp+arg_18]; HKEY
0x18003a000  mov     rcx, rbx; this
0x18003a003  call    ?Initialize@IndexEnumerator@@QEAAJPEAUHKEY__@@0@Z; IndexEnumerator::Initialize(HKEY__ *,HKEY__ *)
0x18003a008  mov     edi, eax
0x18003a00a  test    eax, eax
0x18003a00c  jns     short loc_18003A01D
0x18003a00e  test    rbx, rbx
0x18003a011  jz      short loc_18003A032
0x18003a013  mov     rcx, rbx; this
0x18003a016  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18003a01b  jmp     short loc_18003A032
0x18003a01d  mov     rdx, rbx
0x18003a020  mov     rcx, rsi
0x18003a023  call    ??4?$AutoRef@VIndexEnumerator@@@wmi@@QEAAAEAV01@PEAVIndexEnumerator@@@Z; wmi::AutoRef<IndexEnumerator>::operator=(IndexEnumerator *)
0x18003a028  nop
0x18003a029  lea     rcx, [rbp+var_10]
0x18003a02d  call    ?Release@?$AutoRef@VJobBucket@@@wmi@@QEAAXXZ; wmi::AutoRef<JobBucket>::Release(void)
0x18003a032  lea     rbx, WPP_GLOBAL_Control
0x18003a039  mov     r10, cs:WPP_GLOBAL_Control
0x18003a040  cmp     r10, rbx
0x18003a043  jz      short loc_18003A079
0x18003a045  test    dword ptr [r10+1Ch], 40000h
0x18003a04d  jz      short loc_18003A079
0x18003a04f  mov     ecx, edi
0x18003a051  sar     ecx, 1Fh
0x18003a054  and     ecx, 0FFFFFFFEh
0x18003a057  add     ecx, 4
0x18003a05a  movzx   eax, byte ptr [r10+19h]
0x18003a05f  cmp     eax, ecx
0x18003a061  jb      short loc_18003A079
0x18003a063  mov     edx, 64h ; 'd'
0x18003a068  mov     dword ptr [rsp+40h+phkResult], edi
0x18003a06c  mov     r9d, r14d
0x18003a06f  mov     rcx, [r10+10h]
0x18003a073  call    WPP_SF_dD
0x18003a078  nop
0x18003a079  mov     rcx, [rbp+hKey]; hKey
0x18003a07d  test    rcx, rcx
0x18003a080  jz      short loc_18003A090
0x18003a082  call    cs:__imp_RegCloseKey
0x18003a088  mov     [rbp+hKey], 0
0x18003a090  mov     rcx, [rbp+arg_18]; hKey
0x18003a094  test    rcx, rcx
0x18003a097  jz      short loc_18003A0A7
0x18003a099  call    cs:__imp_RegCloseKey
0x18003a09f  mov     [rbp+arg_18], 0
0x18003a0a7  mov     rcx, [rbp+lpSubKey]; bstrString
0x18003a0ab  call    cs:__imp_SysFreeString
0x18003a0b1  mov     eax, edi
0x18003a0b3  add     rsp, 40h
0x18003a0b7  pop     r14
0x18003a0b9  pop     rdi
0x18003a0ba  pop     rsi
0x18003a0bb  pop     rbx
0x18003a0bc  pop     rbp
0x18003a0bd  retn
```
