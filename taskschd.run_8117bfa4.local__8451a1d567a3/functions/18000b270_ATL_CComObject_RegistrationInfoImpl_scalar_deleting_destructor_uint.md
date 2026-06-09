# ATL::CComObject<RegistrationInfoImpl>::`scalar deleting destructor'(uint)

- ea: `0x18000b270`
- end: `0x18000b555`
- name: `??_G?$CComObject@VRegistrationInfoImpl@@@ATL@@UEAAPEAXI@Z`
- size: `741`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000b270`
- `0x18000b55c`
- `0x180058010`

## import_xrefs

- `msvcrt!free` at `0x18000b53d`
- `msvcrt!free` at `0x18000b53d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b40f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b40f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b2c9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b301`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b315`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b329`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b33d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b351`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b365`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b37c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b396`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b435`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b448`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b46e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b481`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b491`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b501`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b2ed`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b301`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b315`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b329`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b33d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b351`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b365`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b37c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b396`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3d0`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b3ea`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b435`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b448`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b46e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b481`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b491`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4b1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4e1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b4f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b501`
- `OLEAUT32!__imp_VariantClear` at `0x18000b45b`
- `OLEAUT32!__imp_VariantClear` at `0x18000b45b`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000b3bd`
- `OLEAUT32!__imp_VariantChangeType` at `0x18000b3bd`

## pseudocode

```c
char *__fastcall ATL::CComObject<RegistrationInfoImpl>::`scalar deleting destructor'(char *Block, char a2)
{
  char *v3; // rdi
  __int64 v5; // rbp

  v3 = Block + 8;
  if ( !Block )
    v3 = 0;
  *(_QWORD *)Block = &ATL::CComObject<RegistrationInfoImpl>::`vftable';
  *((_DWORD *)Block + 2) = -1073741823;
  if ( v3 )
  {
    v5 = (__int64)(v3 + 8);
    EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 8));
  }
  else
  {
    v5 = 8;
  }
  SysFreeString(*((BSTR *)Block + 8));
  *((_QWORD *)Block + 8) = 0;
  SysFreeString(*((BSTR *)Block + 9));
  *((_QWORD *)Block + 9) = 0;
  SysFreeString(*((BSTR *)Block + 10));
  *((_QWORD *)Block + 10) = 0;
  SysFreeString(*((BSTR *)Block + 11));
  *((_QWORD *)Block + 11) = 0;
  SysFreeString(*((BSTR *)Block + 12));
  *((_QWORD *)Block + 12) = 0;
  SysFreeString(*((BSTR *)Block + 13));
  *((_QWORD *)Block + 13) = 0;
  SysFreeString(*((BSTR *)Block + 14));
  *((_QWORD *)Block + 14) = 0;
  SysFreeString(*((BSTR *)Block + 15));
  *((_QWORD *)Block + 15) = 0;
  SysFreeString(*((BSTR *)Block + 16));
  *((_QWORD *)Block + 16) = 0;
  SysFreeString(*((BSTR *)Block + 17));
  *((_QWORD *)Block + 17) = 0;
  VariantChangeType((VARIANTARG *)Block + 6, (const VARIANTARG *)Block + 6, 0, 0);
  SysFreeString(*((BSTR *)Block + 21));
  *((_QWORD *)Block + 21) = 0;
  SysFreeString(*((BSTR *)Block + 22));
  *((_QWORD *)Block + 22) = 0;
  if ( v3 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  SysFreeString(*((BSTR *)Block + 22));
  SysFreeString(*((BSTR *)Block + 21));
  VariantClear((VARIANTARG *)Block + 6);
  SysFreeString(*((BSTR *)Block + 17));
  SysFreeString(*((BSTR *)Block + 16));
  SysFreeString(*((BSTR *)Block + 15));
  SysFreeString(*((BSTR *)Block + 14));
  SysFreeString(*((BSTR *)Block + 13));
  SysFreeString(*((BSTR *)Block + 12));
  SysFreeString(*((BSTR *)Block + 11));
  SysFreeString(*((BSTR *)Block + 10));
  SysFreeString(*((BSTR *)Block + 9));
  SysFreeString(*((BSTR *)Block + 8));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(Block + 16));
  if ( (a2 & 1) != 0 )
    free(Block);
  return Block;
}

```

## disassembly

```asm
0x18000b270  push    rbx
0x18000b272  sub     rsp, 30h
0x18000b276  mov     [rsp+38h+arg_0], rbp
0x18000b27b  lea     rax, ??_7?$CComObject@VRegistrationInfoImpl@@@ATL@@6B@; const ATL::CComObject<RegistrationInfoImpl>::`vftable'
0x18000b282  mov     [rsp+38h+arg_8], rsi
0x18000b287  mov     rbx, rcx
0x18000b28a  mov     [rsp+38h+arg_10], rdi
0x18000b28f  lea     rdi, [rcx+8]
0x18000b293  mov     [rsp+38h+arg_18], r12
0x18000b298  xor     r12d, r12d
0x18000b29b  test    rcx, rcx
0x18000b29e  mov     [rsp+38h+var_10], r14
0x18000b2a3  mov     [rsp+38h+var_18], r15
0x18000b2a8  mov     r14d, edx
0x18000b2ab  cmovz   rdi, r12
0x18000b2af  mov     [rcx], rax
0x18000b2b2  mov     dword ptr [rcx+8], 0C0000001h
0x18000b2b9  test    rdi, rdi
0x18000b2bc  jz      loc_18000B54B
0x18000b2c2  lea     rbp, [rdi+8]
0x18000b2c6  mov     rcx, rbp; lpCriticalSection
0x18000b2c9  call    cs:__imp_EnterCriticalSection
0x18000b2d0  nop     dword ptr [rax+rax+00h]
0x18000b2d5  mov     rcx, [rbx+40h]; bstrString
0x18000b2d9  call    cs:__imp_SysFreeString
0x18000b2e0  nop     dword ptr [rax+rax+00h]
0x18000b2e5  mov     [rbx+40h], r12
0x18000b2e9  mov     rcx, [rbx+48h]; bstrString
0x18000b2ed  call    cs:__imp_SysFreeString
0x18000b2f4  nop     dword ptr [rax+rax+00h]
0x18000b2f9  mov     [rbx+48h], r12
0x18000b2fd  mov     rcx, [rbx+50h]; bstrString
0x18000b301  call    cs:__imp_SysFreeString
0x18000b308  nop     dword ptr [rax+rax+00h]
0x18000b30d  mov     [rbx+50h], r12
0x18000b311  mov     rcx, [rbx+58h]; bstrString
0x18000b315  call    cs:__imp_SysFreeString
0x18000b31c  nop     dword ptr [rax+rax+00h]
0x18000b321  mov     [rbx+58h], r12
0x18000b325  mov     rcx, [rbx+60h]; bstrString
0x18000b329  call    cs:__imp_SysFreeString
0x18000b330  nop     dword ptr [rax+rax+00h]
0x18000b335  mov     [rbx+60h], r12
0x18000b339  mov     rcx, [rbx+68h]; bstrString
0x18000b33d  call    cs:__imp_SysFreeString
0x18000b344  nop     dword ptr [rax+rax+00h]
0x18000b349  mov     [rbx+68h], r12
0x18000b34d  mov     rcx, [rbx+70h]; bstrString
0x18000b351  call    cs:__imp_SysFreeString
0x18000b358  nop     dword ptr [rax+rax+00h]
0x18000b35d  mov     [rbx+70h], r12
0x18000b361  mov     rcx, [rbx+78h]; bstrString
0x18000b365  call    cs:__imp_SysFreeString
0x18000b36c  nop     dword ptr [rax+rax+00h]
0x18000b371  mov     [rbx+78h], r12
0x18000b375  mov     rcx, [rbx+80h]; bstrString
0x18000b37c  call    cs:__imp_SysFreeString
0x18000b383  nop     dword ptr [rax+rax+00h]
0x18000b388  mov     [rbx+80h], r12
0x18000b38f  mov     rcx, [rbx+88h]; bstrString
0x18000b396  call    cs:__imp_SysFreeString
0x18000b39d  nop     dword ptr [rax+rax+00h]
0x18000b3a2  xor     r9d, r9d; vt
0x18000b3a5  mov     [rbx+88h], r12
0x18000b3ac  xor     r8d, r8d; wFlags
0x18000b3af  lea     rdx, [rbx+90h]; pvarSrc
0x18000b3b6  lea     rcx, [rbx+90h]; pvargDest
0x18000b3bd  call    cs:__imp_VariantChangeType
0x18000b3c4  nop     dword ptr [rax+rax+00h]
0x18000b3c9  mov     rcx, [rbx+0A8h]; bstrString
0x18000b3d0  call    cs:__imp_SysFreeString
0x18000b3d7  nop     dword ptr [rax+rax+00h]
0x18000b3dc  mov     [rbx+0A8h], r12
0x18000b3e3  mov     rcx, [rbx+0B0h]; bstrString
0x18000b3ea  call    cs:__imp_SysFreeString
0x18000b3f1  nop     dword ptr [rax+rax+00h]
0x18000b3f6  test    rdi, rdi
0x18000b3f9  mov     [rbx+0B0h], r12
0x18000b400  mov     rdi, [rsp+38h+arg_10]
0x18000b405  mov     r12, [rsp+38h+arg_18]
0x18000b40a  jz      short loc_18000B41B
0x18000b40c  mov     rcx, rbp; lpCriticalSection
0x18000b40f  call    cs:__imp_LeaveCriticalSection
0x18000b416  nop     dword ptr [rax+rax+00h]
0x18000b41b  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b422  mov     rax, [rcx]
0x18000b425  mov     rax, [rax+10h]
0x18000b429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b42e  mov     rcx, [rbx+0B0h]; bstrString
0x18000b435  call    cs:__imp_SysFreeString
0x18000b43c  nop     dword ptr [rax+rax+00h]
0x18000b441  mov     rcx, [rbx+0A8h]; bstrString
0x18000b448  call    cs:__imp_SysFreeString
0x18000b44f  nop     dword ptr [rax+rax+00h]
0x18000b454  lea     rcx, [rbx+90h]; pvarg
0x18000b45b  call    cs:__imp_VariantClear
0x18000b462  nop     dword ptr [rax+rax+00h]
0x18000b467  mov     rcx, [rbx+88h]; bstrString
0x18000b46e  call    cs:__imp_SysFreeString
0x18000b475  nop     dword ptr [rax+rax+00h]
0x18000b47a  mov     rcx, [rbx+80h]; bstrString
0x18000b481  call    cs:__imp_SysFreeString
0x18000b488  nop     dword ptr [rax+rax+00h]
0x18000b48d  mov     rcx, [rbx+78h]; bstrString
0x18000b491  call    cs:__imp_SysFreeString
0x18000b498  nop     dword ptr [rax+rax+00h]
0x18000b49d  mov     rcx, [rbx+70h]; bstrString
0x18000b4a1  call    cs:__imp_SysFreeString
0x18000b4a8  nop     dword ptr [rax+rax+00h]
0x18000b4ad  mov     rcx, [rbx+68h]; bstrString
0x18000b4b1  call    cs:__imp_SysFreeString
0x18000b4b8  nop     dword ptr [rax+rax+00h]
0x18000b4bd  mov     rcx, [rbx+60h]; bstrString
0x18000b4c1  call    cs:__imp_SysFreeString
0x18000b4c8  nop     dword ptr [rax+rax+00h]
0x18000b4cd  mov     rcx, [rbx+58h]; bstrString
0x18000b4d1  call    cs:__imp_SysFreeString
0x18000b4d8  nop     dword ptr [rax+rax+00h]
0x18000b4dd  mov     rcx, [rbx+50h]; bstrString
0x18000b4e1  call    cs:__imp_SysFreeString
0x18000b4e8  nop     dword ptr [rax+rax+00h]
0x18000b4ed  mov     rcx, [rbx+48h]; bstrString
0x18000b4f1  call    cs:__imp_SysFreeString
0x18000b4f8  nop     dword ptr [rax+rax+00h]
0x18000b4fd  mov     rcx, [rbx+40h]; bstrString
0x18000b501  call    cs:__imp_SysFreeString
0x18000b508  nop     dword ptr [rax+rax+00h]
0x18000b50d  lea     rcx, [rbx+10h]; this
0x18000b511  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x18000b516  mov     r15, [rsp+38h+var_18]
0x18000b51b  test    r14b, 1
0x18000b51f  mov     r14, [rsp+38h+var_10]
0x18000b524  mov     rsi, [rsp+38h+arg_8]
0x18000b529  mov     rbp, [rsp+38h+arg_0]
0x18000b52e  jnz     short loc_18000B53A
0x18000b530  mov     rax, rbx
0x18000b533  add     rsp, 30h
0x18000b537  pop     rbx
0x18000b538  retn
0x18000b53a  mov     rcx, rbx; Block
0x18000b53d  call    cs:__imp_free
0x18000b544  nop     dword ptr [rax+rax+00h]
0x18000b549  jmp     short loc_18000B530
0x18000b54b  mov     ebp, 8
0x18000b550  jmp     loc_18000B2D5
```
