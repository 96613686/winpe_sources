# ?get_LastRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z

- ea: `0x18002c030`
- end: `0x18002c20c`
- name: `?get_LastRunTime@?QIRegisteredTask@@RegisteredTaskImpl@@UEAAJPEAN@Z`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800017f0`
- `0x18002c030`
- `0x18002c214`
- `0x18002c2d0`
- `0x18004e950`
- `0x180054010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c13f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c0bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c13f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c08b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c08b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall _get_LastRunTime__QIRegisteredTask__RegisteredTaskImpl__UEAAJPEAN_Z(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rdi
  const unsigned __int16 *v5; // rdx
  int LastRunInfo; // ebx
  RpcSession *v8; // rcx
  int v9; // eax
  bool v10; // zf
  unsigned int v11; // [rsp+34h] [rbp-44h] BYREF
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF
  int v13; // [rsp+40h] [rbp-38h]
  __int64 v14; // [rsp+48h] [rbp-30h]
  struct _SYSTEMTIME v15; // [rsp+50h] [rbp-28h] BYREF

  if ( !a2 )
    return 2147500035LL;
  v15 = 0;
  v11 = 0;
  v4 = (a1 + 16) & -(__int64)(a1 != 0);
  if ( v4 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  v14 = v4;
  v5 = (const unsigned __int16 *)(a1 + 80);
  if ( *(_QWORD *)(a1 + 104) >= 8u )
    v5 = *(const unsigned __int16 **)v5;
  if ( !*(_DWORD *)(a1 + 128) )
  {
    LastRunInfo = -2147023645;
    goto LABEL_8;
  }
  v8 = *(RpcSession **)(a1 + 136);
  if ( v8 )
  {
    LastRunInfo = RpcSession::GetLastRunInfo(v8, v5, &v15, &v11);
  }
  else
  {
    if ( v5 && *v5 == 92 )
      ++v5;
    v12 = 0;
    LastRunInfo = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, GUID *, __int64 *))(**(_QWORD **)(a1 + 144)
                                                                                                 + 48LL))(
                    *(_QWORD *)(a1 + 144),
                    v5,
                    &GUID_148bd524_a2ab_11ce_b11f_00aa00530503,
                    &v12);
    if ( LastRunInfo < 0
      || (LastRunInfo = (*(__int64 (__fastcall **)(__int64, struct _SYSTEMTIME *))(*(_QWORD *)v12 + 120LL))(v12, &v15),
          LastRunInfo < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      goto LABEL_8;
    }
    v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v12 + 136LL))(v12, &v11);
    v10 = LastRunInfo == 267011;
    LastRunInfo = v9;
    if ( v10 && v9 < 0 )
    {
      v11 = (unsigned __int16)v9;
      LastRunInfo = 267011;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  }
  if ( LastRunInfo < 0 )
  {
LABEL_8:
    if ( v4 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
    return (unsigned int)LastRunInfo;
  }
  v12 = 0;
  v13 = 0;
  ATL::AtlConvertSystemTimeToVariantTime(&v15, (double *)&v12);
  *a2 = v12;
  if ( v4 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v4 + 8));
  return (unsigned int)LastRunInfo;
}

```

## disassembly

```asm
0x18002c030  mov     [rsp+arg_10], rbx
0x18002c035  mov     [rsp+arg_18], rsi
0x18002c03a  push    rdi
0x18002c03b  sub     rsp, 70h
0x18002c03f  mov     rax, cs:__security_cookie
0x18002c046  xor     rax, rsp
0x18002c049  mov     [rsp+78h+var_18], rax
0x18002c04e  mov     rsi, rdx
0x18002c051  mov     rbx, rcx
0x18002c054  test    rdx, rdx
0x18002c057  jz      loc_18002C14D
0x18002c05d  mov     [rsp+78h+var_48], 0
0x18002c065  xorps   xmm0, xmm0
0x18002c068  movups  xmmword ptr [rsp+78h+var_28.wYear], xmm0
0x18002c06d  mov     [rsp+78h+var_44], 0
0x18002c075  mov     rax, rcx
0x18002c078  add     rcx, 10h
0x18002c07c  neg     rax
0x18002c07f  sbb     rdi, rdi
0x18002c082  and     rdi, rcx
0x18002c085  jz      short loc_18002C091
0x18002c087  lea     rcx, [rdi+8]; lpCriticalSection
0x18002c08b  call    cs:__imp_EnterCriticalSection
0x18002c091  mov     [rsp+78h+var_30], rdi
0x18002c096  lea     rdx, [rbx+50h]
0x18002c09a  cmp     qword ptr [rdx+18h], 8
0x18002c09f  jb      short loc_18002C0A4
0x18002c0a1  mov     rdx, [rdx]; unsigned __int16 *
0x18002c0a4  cmp     dword ptr [rbx+80h], 0
0x18002c0ab  jnz     short loc_18002C0E6
0x18002c0ad  mov     ebx, 800704E3h
0x18002c0b2  mov     [rsp+78h+var_48], ebx
0x18002c0b6  test    rdi, rdi
0x18002c0b9  jz      short loc_18002C0C5
0x18002c0bb  lea     rcx, [rdi+8]; lpCriticalSection
0x18002c0bf  call    cs:__imp_LeaveCriticalSection
0x18002c0c5  mov     eax, ebx
0x18002c0c7  mov     rcx, [rsp+78h+var_18]
0x18002c0cc  xor     rcx, rsp; StackCookie
0x18002c0cf  call    __security_check_cookie
0x18002c0d4  lea     r11, [rsp+78h+var_8]
0x18002c0d9  mov     rbx, [r11+20h]
0x18002c0dd  mov     rsi, [r11+28h]
0x18002c0e1  mov     rsp, r11
0x18002c0e4  pop     rdi
0x18002c0e5  retn
0x18002c0e6  mov     rcx, [rbx+88h]; this
0x18002c0ed  test    rcx, rcx
0x18002c0f0  jz      short loc_18002C157
0x18002c0f2  lea     r9, [rsp+78h+var_44]; unsigned int *
0x18002c0f7  lea     r8, [rsp+78h+var_28]; struct _SYSTEMTIME *
0x18002c0fc  call    ?GetLastRunInfo@RpcSession@@QEBAJPEBGPEAU_SYSTEMTIME@@PEAK@Z; RpcSession::GetLastRunInfo(ushort const *,_SYSTEMTIME *,ulong *)
0x18002c101  mov     ebx, eax
0x18002c103  mov     [rsp+78h+var_48], ebx
0x18002c107  test    ebx, ebx
0x18002c109  js      short loc_18002C0B6
0x18002c10b  xorps   xmm0, xmm0
0x18002c10e  movsd   [rsp+78h+var_40], xmm0
0x18002c114  mov     [rsp+78h+var_38], 0
0x18002c11c  lea     rdx, [rsp+78h+var_40]; double *
0x18002c121  lea     rcx, [rsp+78h+var_28]; struct _SYSTEMTIME *
0x18002c126  call    ?AtlConvertSystemTimeToVariantTime@ATL@@YAHAEBU_SYSTEMTIME@@PEAN@Z; ATL::AtlConvertSystemTimeToVariantTime(_SYSTEMTIME const &,double *)
0x18002c12b  nop
0x18002c12c  movsd   xmm0, [rsp+78h+var_40]
0x18002c132  movsd   qword ptr [rsi], xmm0
0x18002c136  test    rdi, rdi
0x18002c139  jz      short loc_18002C146
0x18002c13b  lea     rcx, [rdi+8]; lpCriticalSection
0x18002c13f  call    cs:__imp_LeaveCriticalSection
0x18002c145  nop
0x18002c146  mov     eax, ebx
0x18002c148  jmp     loc_18002C0C7
0x18002c14d  mov     eax, 80004003h
0x18002c152  jmp     loc_18002C0C7
0x18002c157  test    rdx, rdx
0x18002c15a  jz      short loc_18002C166
0x18002c15c  cmp     word ptr [rdx], 5Ch ; '\'
0x18002c160  jnz     short loc_18002C166
0x18002c162  add     rdx, 2
0x18002c166  mov     [rsp+78h+var_40], 0
0x18002c16f  mov     rcx, [rbx+90h]
0x18002c176  mov     rax, [rcx]
0x18002c179  lea     r9, [rsp+78h+var_40]
0x18002c17e  lea     r8, _GUID_148bd524_a2ab_11ce_b11f_00aa00530503
0x18002c185  mov     rax, [rax+30h]
0x18002c189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c18e  mov     ebx, eax
0x18002c190  test    eax, eax
0x18002c192  js      short loc_18002C1E5
0x18002c194  mov     rcx, [rsp+78h+var_40]
0x18002c199  mov     rax, [rcx]
0x18002c19c  lea     rdx, [rsp+78h+var_28]
0x18002c1a1  mov     rax, [rax+78h]
0x18002c1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1aa  mov     ebx, eax
0x18002c1ac  test    eax, eax
0x18002c1ae  js      short loc_18002C1E5
0x18002c1b0  mov     rcx, [rsp+78h+var_40]
0x18002c1b5  lea     rdx, [rsp+78h+var_44]
0x18002c1ba  mov     rax, [rcx]
0x18002c1bd  mov     rax, [rax+88h]
0x18002c1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c1c9  cmp     ebx, 41303h
0x18002c1cf  mov     ebx, eax
0x18002c1d1  jnz     short loc_18002C1F4
0x18002c1d3  test    eax, eax
0x18002c1d5  jns     short loc_18002C1F4
0x18002c1d7  movzx   eax, ax
0x18002c1da  mov     [rsp+78h+var_44], eax
0x18002c1de  mov     ebx, 41303h
0x18002c1e3  jmp     short loc_18002C1F4
0x18002c1e5  lea     rcx, [rsp+78h+var_40]
0x18002c1ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002c1ef  jmp     loc_18002C0B2
0x18002c1f4  lea     rcx, [rsp+78h+var_40]
0x18002c1f9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002c1fe  jmp     loc_18002C103
0x18002c203  mov     ebx, [rsp+78h+var_48]
0x18002c207  jmp     loc_18002C146
```
