# GetIsFHConfigured(bool &)

- ea: `0x1800191dc`
- end: `0x180019281`
- name: `?GetIsFHConfigured@@YAJAEA_N@Z`
- size: `165`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018ea0`

## callees

- `0x180013ae4`
- `0x1800152d4`
- `0x1800191dc`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001921d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001921d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetIsFHConfigured(bool *a1)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v8; // [rsp+40h] [rbp+8h] BYREF

  *a1 = 0;
  v8 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
  v2 = CoCreateInstance(&CLSID_FhConfigMgr, 0, 1u, &GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4, &v8);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 232LL))(v8);
    v3 = v2;
    if ( v2 >= 0 )
    {
      *a1 = 1;
      v3 = 0;
      goto LABEL_7;
    }
    v4 = 2247;
  }
  else
  {
    v4 = 2245;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storageusage\\storagegrovelerscans.cpp",
    (const char *)(unsigned int)v2,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v8);
  return v3;
}

```

## disassembly

```asm
0x1800191dc  mov     [rsp+arg_8], rbx
0x1800191e1  push    rdi
0x1800191e2  sub     rsp, 30h
0x1800191e6  mov     rdi, rcx
0x1800191e9  mov     byte ptr [rcx], 0
0x1800191ec  mov     [rsp+38h+arg_0], 0
0x1800191f5  lea     rcx, [rsp+38h+arg_0]
0x1800191fa  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800191ff  lea     rax, [rsp+38h+arg_0]
0x180019204  mov     qword ptr [rsp+38h+ppv], rax; int
0x180019209  lea     r9, _GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4; riid
0x180019210  xor     edx, edx; pUnkOuter
0x180019212  lea     r8d, [rdx+1]; dwClsContext
0x180019216  lea     rcx, CLSID_FhConfigMgr; rclsid
0x18001921d  call    cs:__imp_CoCreateInstance
0x180019223  mov     ebx, eax
0x180019225  test    eax, eax
0x180019227  jns     short loc_180019230
0x180019229  mov     edx, 8C5h
0x18001922e  jmp     short loc_18001924F
0x180019230  mov     rcx, [rsp+38h+arg_0]
0x180019235  mov     rax, [rcx]
0x180019238  mov     rax, [rax+0E8h]
0x18001923f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019244  mov     ebx, eax
0x180019246  test    eax, eax
0x180019248  jns     short loc_180019265
0x18001924a  mov     edx, 8C7h; void *
0x18001924f  lea     r8, aOnecoreDrivers; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180019256  mov     r9d, eax; char *
0x180019259  mov     rcx, [rsp+38h]; this
0x18001925e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019263  jmp     short loc_18001926A
0x180019265  mov     byte ptr [rdi], 1
0x180019268  xor     ebx, ebx
0x18001926a  lea     rcx, [rsp+38h+arg_0]
0x18001926f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180019274  mov     eax, ebx
0x180019276  mov     rbx, [rsp+38h+arg_8]
0x18001927b  add     rsp, 30h
0x18001927f  pop     rdi
0x180019280  retn
```
