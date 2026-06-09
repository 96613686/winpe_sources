# LocationDataSource::ShutdownInDisconnectableContext(tagComCallData *)

- ea: `0x180011ff0`
- end: `0x18001216f`
- name: `?ShutdownInDisconnectableContext@LocationDataSource@@CAJPEAUtagComCallData@@@Z`
- size: `383`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000166c`
- `0x1800018fc`
- `0x180006844`
- `0x18000cfec`
- `0x180011b0c`
- `0x180011ff0`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18001214e`
- `api-ms-win-core-com-l1-1-0!CoDisconnectContext` at `0x18001214e`

## pseudocode

```c
__int64 __fastcall LocationDataSource::ShutdownInDisconnectableContext(struct tagComCallData *a1)
{
  _QWORD *pUserDefined; // rsi
  int (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall *v3)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // ebx
  _BYTE v12[32]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v13; // [rsp+50h] [rbp-39h]
  __int64 v14; // [rsp+58h] [rbp-31h]
  __int64 v15; // [rsp+F0h] [rbp+67h] BYREF
  int (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v17; // [rsp+100h] [rbp+77h] BYREF

  pUserDefined = a1->pUserDefined;
  v2 = (int (__fastcall ***)(_QWORD, GUID *, __int64 *))pUserDefined[6];
  v16 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v2;
  if ( v2 )
  {
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v2)[1])(v2);
    v15 = 0;
    v3 = **v2;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
    if ( v3(v2, &GUID_00000036_0000_0000_c000_000000000046, &v15) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 72LL))(v15);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 80LL))(v15);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(pUserDefined + 6);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 *)&v16);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
  }
  Cache::Lock((struct Cache *)*pUserDefined, (Cache::Proxy *)v12);
  if ( *(_BYTE *)(v13 + 1) )
  {
    if ( pUserDefined[8] )
    {
      v4 = pUserDefined[4];
      if ( v4 )
      {
        v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 128LL))(v4);
        if ( v5 < 0 )
        {
          if ( (unsigned int)dword_180030000 > 5
            && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL, (unsigned int)v5) )
          {
            LODWORD(v15) = v8;
            v17 = 0x1000000;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v7,
              (__int64)byte_180028C21,
              v8,
              v9,
              (__int64)&v17,
              (__int64)&v15);
          }
        }
        else
        {
          pUserDefined[8] = 0;
        }
      }
    }
    if ( *(_BYTE *)(v13 + 1) )
    {
      *(_BYTE *)(v13 + 1) = 0;
      *(_BYTE *)(v14 + 120) = 1;
    }
  }
  Cache::Proxy::~Proxy((Cache::Proxy *)v12);
  v10 = CoDisconnectContext(0xFFFFFFFF);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((__int64 *)&v16);
  return v10;
}

```

## disassembly

```asm
0x180011ff0  push    rbp
0x180011ff2  push    rbx
0x180011ff3  push    rsi
0x180011ff4  push    rdi
0x180011ff5  push    r14
0x180011ff7  lea     rbp, [rsp-37h]
0x180011ffc  sub     rsp, 0C0h
0x180012003  mov     rsi, [rcx+8]
0x180012007  mov     rbx, [rsi+30h]
0x18001200b  mov     [rbp+57h+arg_8], rbx
0x18001200f  test    rbx, rbx
0x180012012  jz      short loc_180012024
0x180012014  mov     rax, [rbx]
0x180012017  mov     rcx, rbx
0x18001201a  mov     rax, [rax+8]
0x18001201e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012023  nop
0x180012024  test    rbx, rbx
0x180012027  jz      short loc_180012097
0x180012029  mov     [rbp+57h+arg_0], 0
0x180012031  mov     rax, [rbx]
0x180012034  mov     rdi, [rax]
0x180012037  lea     rcx, [rbp+57h+arg_0]
0x18001203b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180012040  lea     r8, [rbp+57h+arg_0]
0x180012044  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001204b  mov     rcx, rbx
0x18001204e  mov     rax, rdi
0x180012051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012056  nop
0x180012057  test    eax, eax
0x180012059  js      short loc_18001207B
0x18001205b  mov     rcx, [rbp+57h+arg_0]
0x18001205f  mov     rax, [rcx]
0x180012062  mov     rax, [rax+48h]
0x180012066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001206b  mov     rcx, [rbp+57h+arg_0]
0x18001206f  mov     rax, [rcx]
0x180012072  mov     rax, [rax+50h]
0x180012076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001207b  lea     rcx, [rsi+30h]
0x18001207f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180012084  lea     rcx, [rbp+57h+arg_8]
0x180012088  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001208d  nop
0x18001208e  lea     rcx, [rbp+57h+arg_0]
0x180012092  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180012097  lea     rdx, [rbp+57h+var_B0]
0x18001209b  mov     rcx, [rsi]
0x18001209e  call    ?Lock@Cache@@QEAA?AVProxy@1@XZ; Cache::Lock(void)
0x1800120a3  nop
0x1800120a4  mov     rax, [rbp+57h+var_90]
0x1800120a8  cmp     byte ptr [rax+1], 0
0x1800120ac  jz      loc_180012142
0x1800120b2  mov     rdx, [rsi+40h]
0x1800120b6  test    rdx, rdx
0x1800120b9  jz      short loc_18001212C
0x1800120bb  mov     rcx, [rsi+20h]
0x1800120bf  test    rcx, rcx
0x1800120c2  jz      short loc_18001212C
0x1800120c4  mov     rax, [rcx]
0x1800120c7  mov     rax, [rax+80h]
0x1800120ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120d3  mov     r8d, eax
0x1800120d6  test    eax, eax
0x1800120d8  js      short loc_1800120E4
0x1800120da  mov     qword ptr [rsi+40h], 0
0x1800120e2  jmp     short loc_18001212C
0x1800120e4  mov     eax, cs:dword_180030000
0x1800120ea  cmp     eax, 5
0x1800120ed  jbe     short loc_18001212C
0x1800120ef  mov     rdx, 200000000000h
0x1800120f9  call    _tlgKeywordOn
0x1800120fe  test    al, al
0x180012100  jz      short loc_18001212C
0x180012102  mov     dword ptr [rbp+57h+arg_0], r8d
0x180012106  mov     [rbp+57h+arg_10], 1000000h
0x18001210e  lea     rax, [rbp+57h+arg_0]
0x180012112  mov     [rsp+0E0h+var_B8], rax
0x180012117  lea     rax, [rbp+57h+arg_10]
0x18001211b  mov     [rsp+0E0h+var_C0], rax
0x180012120  lea     rdx, byte_180028C21
0x180012127  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18001212c  mov     rax, [rbp+57h+var_90]
0x180012130  cmp     byte ptr [rax+1], 0
0x180012134  jz      short loc_180012142
0x180012136  mov     byte ptr [rax+1], 0
0x18001213a  mov     rax, [rbp+57h+var_88]
0x18001213e  mov     byte ptr [rax+78h], 1
0x180012142  lea     rcx, [rbp+57h+var_B0]; this
0x180012146  call    ??1Proxy@Cache@@QEAA@XZ; Cache::Proxy::~Proxy(void)
0x18001214b  or      ecx, 0FFFFFFFFh; dwTimeout
0x18001214e  call    cs:__imp_CoDisconnectContext
0x180012154  mov     ebx, eax
0x180012156  lea     rcx, [rbp+57h+arg_8]
0x18001215a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001215f  mov     eax, ebx
0x180012161  add     rsp, 0C0h
0x180012168  pop     r14
0x18001216a  pop     rdi
0x18001216b  pop     rsi
0x18001216c  pop     rbx
0x18001216d  pop     rbp
0x18001216e  retn
```
