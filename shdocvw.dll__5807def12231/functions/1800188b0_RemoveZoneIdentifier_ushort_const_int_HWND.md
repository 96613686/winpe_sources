# RemoveZoneIdentifier(ushort const *,int,HWND__ *)

- ea: `0x1800188b0`
- end: `0x1800189f4`
- name: `?RemoveZoneIdentifier@@YAJPEBGHPEAUHWND__@@@Z`
- size: `324`
- prototype: `int(const unsigned __int16 *, int, HWND)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003810`
- `0x180018824`

## callees

- `0x180002240`
- `0x1800067a0`
- `0x18000b924`
- `0x180015bc4`
- `0x1800188b0`
- `0x180029010`

## string_xrefs

- `0x180018926`: `onecoreuap\internal\shell\inc\private\SecurityZoneHelpers.h`
- `0x180018990`: `onecoreuap\internal\shell\inc\private\SecurityZoneHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RemoveZoneIdentifier(const unsigned __int16 *a1, int a2, HWND a3)
{
  struct _GUID *v6; // rdx
  const struct _GUID *v7; // r8
  HRESULT InstanceAsAdmin; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  void *v11; // rbx
  __int64 (__fastcall *v12)(void *, GUID *, __int64 *); // rdi
  int v13; // eax
  __int64 v14; // rdx
  int v16; // [rsp+20h] [rbp-28h]
  void *v17[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  __int64 v19; // [rsp+88h] [rbp+40h] BYREF

  v17[0] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  if ( a2 )
  {
    InstanceAsAdmin = CoCreateInstanceAsAdmin(a3, v6, v7, v17);
    v9 = InstanceAsAdmin;
    if ( InstanceAsAdmin < 0 )
    {
      v10 = 174;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\SecurityZoneHelpers.h",
        (const char *)(unsigned int)InstanceAsAdmin,
        v16);
      goto LABEL_15;
    }
  }
  else
  {
    InstanceAsAdmin = IECreateInstance(
                        &CLSID_PersistentZoneIdentifier,
                        (struct IUnknown *)v6,
                        1u,
                        &GUID_cd45f185_1b21_48e2_967b_ead743a8914e,
                        v17);
    v9 = InstanceAsAdmin;
    if ( InstanceAsAdmin < 0 )
    {
      v10 = 178;
      goto LABEL_6;
    }
  }
  InstanceAsAdmin = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v17[0] + 40LL))(v17[0]);
  v9 = InstanceAsAdmin;
  if ( InstanceAsAdmin < 0 )
  {
    v10 = 180;
    goto LABEL_6;
  }
  v19 = 0;
  v11 = v17[0];
  v12 = **(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v17[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v13 = v12(v11, &GUID_0000010b_0000_0000_c000_000000000046, &v19);
  v9 = v13;
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v19 + 48LL))(v19, a1, 1);
    v9 = v13;
    if ( v13 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
      v9 = 0;
      goto LABEL_15;
    }
    v14 = 184;
  }
  else
  {
    v14 = 183;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\SecurityZoneHelpers.h",
    (const char *)(unsigned int)v13,
    v16);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
LABEL_15:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  return v9;
}

```

## disassembly

```asm
0x1800188b0  push    rbp
0x1800188b2  push    rbx
0x1800188b3  push    rsi
0x1800188b4  push    rdi
0x1800188b5  mov     rbp, rsp
0x1800188b8  sub     rsp, 48h
0x1800188bc  mov     rdi, r8
0x1800188bf  mov     ebx, edx
0x1800188c1  mov     rsi, rcx
0x1800188c4  mov     [rbp+var_18], 0
0x1800188cc  lea     rcx, [rbp+var_18]
0x1800188d0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800188d5  test    ebx, ebx
0x1800188d7  jz      short loc_1800188F2
0x1800188d9  lea     r9, [rbp+var_18]; void **
0x1800188dd  mov     rcx, rdi; HWND
0x1800188e0  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x1800188e5  mov     ebx, eax
0x1800188e7  test    eax, eax
0x1800188e9  jns     short loc_180018937
0x1800188eb  mov     edx, 0AEh
0x1800188f0  jmp     short loc_18001891F
0x1800188f2  lea     rax, [rbp+var_18]
0x1800188f6  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800188fb  lea     r9, _GUID_cd45f185_1b21_48e2_967b_ead743a8914e; struct _GUID *
0x180018902  mov     r8d, 1; unsigned int
0x180018908  lea     rcx, CLSID_PersistentZoneIdentifier; struct _GUID *
0x18001890f  call    ?IECreateInstance@@YAJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@Z; IECreateInstance(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180018914  mov     ebx, eax
0x180018916  test    eax, eax
0x180018918  jns     short loc_180018937
0x18001891a  mov     edx, 0B2h; void *
0x18001891f  mov     rcx, [rbp+20h]; this
0x180018923  mov     r9d, eax; char *
0x180018926  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18001892d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018932  jmp     loc_1800189E0
0x180018937  mov     rcx, [rbp+var_18]
0x18001893b  mov     rax, [rcx]
0x18001893e  mov     rax, [rax+28h]
0x180018942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018947  mov     ebx, eax
0x180018949  test    eax, eax
0x18001894b  jns     short loc_180018954
0x18001894d  mov     edx, 0B4h
0x180018952  jmp     short loc_18001891F
0x180018954  mov     [rbp+arg_18], 0
0x18001895c  mov     rbx, [rbp+var_18]
0x180018960  mov     rax, [rbx]
0x180018963  mov     rdi, [rax]
0x180018966  lea     rcx, [rbp+arg_18]
0x18001896a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001896f  lea     r8, [rbp+arg_18]
0x180018973  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18001897a  mov     rcx, rbx
0x18001897d  mov     rax, rdi
0x180018980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018985  mov     ebx, eax
0x180018987  test    eax, eax
0x180018989  jns     short loc_1800189AF
0x18001898b  mov     edx, 0B7h; void *
0x180018990  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180018997  mov     r9d, eax; char *
0x18001899a  mov     rcx, [rbp+20h]; this
0x18001899e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800189a3  nop
0x1800189a4  lea     rcx, [rbp+arg_18]
0x1800189a8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800189ad  jmp     short loc_1800189E0
0x1800189af  mov     rcx, [rbp+arg_18]
0x1800189b3  mov     rax, [rcx]
0x1800189b6  mov     r8d, 1
0x1800189bc  mov     rdx, rsi
0x1800189bf  mov     rax, [rax+30h]
0x1800189c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189c8  mov     ebx, eax
0x1800189ca  test    eax, eax
0x1800189cc  jns     short loc_1800189D5
0x1800189ce  mov     edx, 0B8h
0x1800189d3  jmp     short loc_180018990
0x1800189d5  lea     rcx, [rbp+arg_18]
0x1800189d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800189de  xor     ebx, ebx
0x1800189e0  lea     rcx, [rbp+var_18]
0x1800189e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800189e9  mov     eax, ebx
0x1800189eb  add     rsp, 48h
0x1800189ef  pop     rdi
0x1800189f0  pop     rsi
0x1800189f1  pop     rbx
0x1800189f2  pop     rbp
0x1800189f3  retn
```
