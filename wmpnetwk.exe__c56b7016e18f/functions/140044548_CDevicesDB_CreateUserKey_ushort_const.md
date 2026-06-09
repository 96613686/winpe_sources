# CDevicesDB::CreateUserKey(ushort const *)

- ea: `0x140044548`
- end: `0x1400447e9`
- name: `?CreateUserKey@CDevicesDB@@QEAAJPEBG@Z`
- size: `673`
- prototype: `__int64 __fastcall(CDevicesDB *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140056200`

## callees

- `0x140006d70`
- `0x140008eac`
- `0x14000c920`
- `0x140015100`
- `0x14003b08c`
- `0x14003e5f4`
- `0x14003f17c`
- `0x140044548`
- `0x1400447f0`
- `0x140044834`
- `0x140044884`
- `0x140045f20`
- `0x14004a79c`
- `0x140093330`
- `0x140096478`
- `0x14009e010`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x140044610`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140044610`
- `KERNEL32!LocalFree` at `0x140044779`
- `KERNEL32!LocalFree` at `0x140044779`
- `KERNEL32!GetLastError` at `0x14004461a`
- `KERNEL32!GetLastError` at `0x14004461a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CDevicesDB::CreateUserKey(CDevicesDB *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  DWORD LastError; // ebx
  unsigned __int16 *v6; // r9
  const unsigned __int16 *v7; // r8
  bool Account; // bl
  __int64 v9; // rdx
  DWORD v10; // eax
  unsigned int v12; // [rsp+20h] [rbp-99h]
  struct _SECURITY_ATTRIBUTES *v13; // [rsp+30h] [rbp-89h]
  unsigned int *v14; // [rsp+38h] [rbp-81h]
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-79h] BYREF
  PSID Sid; // [rsp+48h] [rbp-71h] BYREF
  __int64 v17; // [rsp+50h] [rbp-69h] BYREF
  void *v18[3]; // [rsp+58h] [rbp-61h] BYREF
  _BYTE v19[88]; // [rsp+70h] [rbp-49h] BYREF
  __int64 v20; // [rsp+C8h] [rbp+Fh]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, a2);
  }
  Sid = 0;
  if ( (*(__int64 (__fastcall **)(CDevicesDB *))(*(_QWORD *)this + 88LL))(this) && a2 )
  {
    v4 = (*(__int64 (__fastcall **)(CDevicesDB *))(*(_QWORD *)this + 88LL))(this);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
      &lpSubKey,
      v4);
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\");
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, a2);
    if ( ConvertStringSidToSidW(a2, &Sid) )
    {
      ATL::CSid::CSid((ATL::CSid *)v19);
      Account = ATL::CSid::LoadAccount((ATL::CSid *)v19, (const struct _SID *)Sid, v7);
      v9 = v20;
      if ( !*(_DWORD *)(v20 - 16) )
      {
        ATL::CSid::GetAccountNameAndDomain((ATL::CSid *)v19);
        v9 = v20;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
        &v17,
        v9);
      if ( !Account || (LastError = 0, !*(_DWORD *)(v17 - 16)) )
        LastError = 1337;
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v17);
      ATL::CSid::~CSid((ATL::CSid *)v19);
    }
    else
    {
      LastError = GetLastError();
      Sid = 0;
    }
    if ( !LastError )
    {
      memset(v18, 0, sizeof(v18));
      v10 = ATL::CRegKey::Create((ATL::CRegKey *)v18, HKEY_LOCAL_MACHINE, lpSubKey, v6, v12, 0xF013Fu, v13, v14);
      LastError = v10;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          140,
          (unsigned int)&WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids,
          (_DWORD)lpSubKey,
          v10);
      }
      if ( !LastError && !(unsigned int)SetHandleACLs((HKEY)v18[0], a2, 4, 0x2001Fu, 3u) )
      {
        LastError = 13;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, 13);
        }
      }
      ATL::CRegKey::Close((ATL::CRegKey *)v18);
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&lpSubKey);
  }
  else
  {
    LastError = 87;
  }
  if ( Sid )
  {
    LocalFree(Sid);
    Sid = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)(LastError != 0 ? 2 : 5) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x140044548  mov     [rsp-8+arg_10], rbx
0x14004454d  push    rbp
0x14004454e  push    rdi
0x14004454f  push    r15
0x140044551  lea     rbp, [rsp-47h]
0x140044556  sub     rsp, 100h
0x14004455d  mov     rax, cs:__security_cookie
0x140044564  xor     rax, rsp
0x140044567  mov     [rbp+57h+var_20], rax
0x14004456b  mov     rdi, rdx
0x14004456e  mov     rbx, rcx
0x140044571  lea     r15, WPP_GLOBAL_Control
0x140044578  mov     rcx, cs:WPP_GLOBAL_Control
0x14004457f  cmp     rcx, r15
0x140044582  jz      short loc_1400445A8
0x140044584  test    byte ptr [rcx+1Ch], 1
0x140044588  jz      short loc_1400445A8
0x14004458a  cmp     byte ptr [rcx+19h], 5
0x14004458e  jb      short loc_1400445A8
0x140044590  mov     edx, 8Bh
0x140044595  mov     r9, rdi
0x140044598  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14004459f  mov     rcx, [rcx+10h]
0x1400445a3  call    WPP_SF_S
0x1400445a8  mov     [rbp+57h+Sid], 0
0x1400445b0  mov     rax, [rbx]
0x1400445b3  mov     rcx, rbx
0x1400445b6  mov     rax, [rax+58h]
0x1400445ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400445bf  test    rax, rax
0x1400445c2  jz      loc_14004476B
0x1400445c8  test    rdi, rdi
0x1400445cb  jz      loc_14004476B
0x1400445d1  mov     rax, [rbx]
0x1400445d4  mov     rcx, rbx
0x1400445d7  mov     rax, [rax+58h]
0x1400445db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400445e0  mov     rdx, rax
0x1400445e3  lea     rcx, [rbp+57h+lpSubKey]
0x1400445e7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x1400445ec  nop
0x1400445ed  lea     rdx, asc_1400A283C; "\\"
0x1400445f4  lea     rcx, [rbp+57h+lpSubKey]
0x1400445f8  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1400445fd  mov     rdx, rdi
0x140044600  lea     rcx, [rbp+57h+lpSubKey]
0x140044604  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x140044609  lea     rdx, [rbp+57h+Sid]; Sid
0x14004460d  mov     rcx, rdi; StringSid
0x140044610  call    cs:__imp_ConvertStringSidToSidW
0x140044616  test    eax, eax
0x140044618  jnz     short loc_14004462C
0x14004461a  call    cs:__imp_GetLastError
0x140044620  mov     ebx, eax
0x140044622  mov     [rbp+57h+Sid], 0
0x14004462a  jmp     short loc_14004468C
0x14004462c  lea     rcx, [rbp+57h+var_A0]; this
0x140044630  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x140044635  nop
0x140044636  mov     rdx, [rbp+57h+Sid]; struct _SID *
0x14004463a  lea     rcx, [rbp+57h+var_A0]; this
0x14004463e  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x140044643  mov     bl, al
0x140044645  mov     rdx, [rbp+57h+var_48]
0x140044649  cmp     dword ptr [rdx-10h], 0
0x14004464d  jnz     short loc_14004465C
0x14004464f  lea     rcx, [rbp+57h+var_A0]; this
0x140044653  call    ?GetAccountNameAndDomain@CSid@ATL@@AEBAXXZ; ATL::CSid::GetAccountNameAndDomain(void)
0x140044658  mov     rdx, [rbp+57h+var_48]
0x14004465c  lea     rcx, [rbp+57h+var_C0]
0x140044660  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(ushort const *)
0x140044665  test    bl, bl
0x140044667  jz      short loc_140044674
0x140044669  xor     ebx, ebx
0x14004466b  mov     rax, [rbp+57h+var_C0]
0x14004466f  cmp     [rax-10h], ebx
0x140044672  jnz     short loc_140044679
0x140044674  mov     ebx, 539h
0x140044679  lea     rcx, [rbp+57h+var_C0]
0x14004467d  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140044682  nop
0x140044683  lea     rcx, [rbp+57h+var_A0]; this
0x140044687  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x14004468c  test    ebx, ebx
0x14004468e  jnz     loc_140044760
0x140044694  mov     [rbp+57h+var_B8], 0
0x14004469c  mov     [rbp+57h+var_B0], 0
0x1400446a4  mov     [rbp+57h+var_A8], 0
0x1400446ac  mov     [rsp+110h+var_E8], 0F013Fh; unsigned int
0x1400446b4  mov     r8, [rbp+57h+lpSubKey]; lpSubKey
0x1400446b8  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400446bf  lea     rcx, [rbp+57h+var_B8]; this
0x1400446c3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1400446c8  mov     ebx, eax
0x1400446ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400446d1  cmp     rcx, r15
0x1400446d4  jz      short loc_1400446FF
0x1400446d6  test    byte ptr [rcx+1Ch], 2
0x1400446da  jz      short loc_1400446FF
0x1400446dc  cmp     byte ptr [rcx+19h], 4
0x1400446e0  jb      short loc_1400446FF
0x1400446e2  mov     edx, 8Ch
0x1400446e7  mov     dword ptr [rsp+110h+var_F0], eax
0x1400446eb  mov     r9, [rbp+57h+lpSubKey]
0x1400446ef  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x1400446f6  mov     rcx, [rcx+10h]
0x1400446fa  call    WPP_SF_Sd
0x1400446ff  test    ebx, ebx
0x140044701  jnz     short loc_140044756
0x140044703  mov     [rsp+110h+var_F0], 3; unsigned __int8
0x140044708  mov     r9d, 2001Fh; unsigned int
0x14004470e  lea     r8d, [rbx+4]; enum _SE_OBJECT_TYPE
0x140044712  mov     rdx, rdi; StringSid
0x140044715  mov     rcx, [rbp+57h+var_B8]; void *
0x140044719  call    ?SetHandleACLs@@YAHPEAXPEBGW4_SE_OBJECT_TYPE@@KE@Z; SetHandleACLs(void *,ushort const *,_SE_OBJECT_TYPE,ulong,uchar)
0x14004471e  test    eax, eax
0x140044720  jnz     short loc_140044756
0x140044722  lea     ebx, [rax+0Dh]
0x140044725  mov     rcx, cs:WPP_GLOBAL_Control
0x14004472c  cmp     rcx, r15
0x14004472f  jz      short loc_140044756
0x140044731  test    byte ptr [rcx+1Ch], 2
0x140044735  jz      short loc_140044756
0x140044737  cmp     byte ptr [rcx+19h], 2
0x14004473b  jb      short loc_140044756
0x14004473d  mov     edx, 8Dh
0x140044742  mov     r9d, ebx
0x140044745  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x14004474c  mov     rcx, [rcx+10h]
0x140044750  call    WPP_SF_d
0x140044755  nop
0x140044756  lea     rcx, [rbp+57h+var_B8]; this
0x14004475a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14004475f  nop
0x140044760  lea     rcx, [rbp+57h+lpSubKey]
0x140044764  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140044769  jmp     short loc_140044770
0x14004476b  mov     ebx, 57h ; 'W'
0x140044770  mov     rcx, [rbp+57h+Sid]; hMem
0x140044774  test    rcx, rcx
0x140044777  jz      short loc_140044787
0x140044779  call    cs:__imp_LocalFree
0x14004477f  mov     [rbp+57h+Sid], 0
0x140044787  mov     rcx, cs:WPP_GLOBAL_Control
0x14004478e  cmp     rcx, r15
0x140044791  jz      short loc_1400447C7
0x140044793  test    byte ptr [rcx+1Ch], 1
0x140044797  jz      short loc_1400447C7
0x140044799  movzx   r9d, byte ptr [rcx+19h]
0x14004479e  mov     eax, ebx
0x1400447a0  neg     eax
0x1400447a2  sbb     edx, edx
0x1400447a4  and     edx, 0FFFFFFFDh
0x1400447a7  add     edx, 5
0x1400447aa  cmp     r9d, edx
0x1400447ad  jb      short loc_1400447C7
0x1400447af  mov     edx, 8Eh
0x1400447b4  mov     r9d, ebx
0x1400447b7  lea     r8, WPP_3f0765ffc2ae3a03ad5dfada532c0697_Traceguids
0x1400447be  mov     rcx, [rcx+10h]
0x1400447c2  call    WPP_SF_d
0x1400447c7  mov     eax, ebx
0x1400447c9  mov     rcx, [rbp+57h+var_20]
0x1400447cd  xor     rcx, rsp; StackCookie
0x1400447d0  call    __security_check_cookie
0x1400447d5  mov     rbx, [rsp+110h+arg_10]
0x1400447dd  add     rsp, 100h
0x1400447e4  pop     r15
0x1400447e6  pop     rdi
0x1400447e7  pop     rbp
0x1400447e8  retn
```
