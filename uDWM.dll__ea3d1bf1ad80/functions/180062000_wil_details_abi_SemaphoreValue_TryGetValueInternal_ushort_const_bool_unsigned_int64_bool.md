# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180062000`
- end: `0x180062285`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `645`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800990a0`

## callees

- `0x1800061e4`
- `0x18004889c`
- `0x180062000`
- `0x18006228c`
- `0x1800623e4`
- `0x1800802e8`
- `0x180081a68`
- `0x180095130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006210d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800621ab`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18006210d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800621ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006211b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006211b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // rax
  WCHAR *v17; // rcx
  wil::details *v18; // rax
  wil::details *v19; // rdi
  const char *v20; // r9
  int ValueFromSemaphore; // eax
  unsigned int v23; // ebx
  wil::details *v24; // rbx
  const char *v25; // r9
  void *v26; // rdx
  int LastError; // esi
  void *v28; // rdx
  int v29; // eax
  int v30; // [rsp+20h] [rbp-E0h] BYREF
  int v31; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v32; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = &Name[v13];
    v16 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v5;
        --v16;
      }
      while ( v16 );
    }
    v17 = v15 - 1;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
  }
  v18 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v18;
  if ( !v18 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v20);
    return 0;
  }
  v31 = 0;
  v30 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v31);
  v23 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v30);
LABEL_27:
    wil::details::CloseHandle(v19, v26);
    return v23;
  }
  StringCchCatW(Name, 0x104u, L"h");
  v32 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v24 = v32;
  if ( (unsigned __int8)std::operator==<CWindowBorder::CCachedBorderBrush>(&v32) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v25);
LABEL_24:
    if ( v24 )
      wil::details::CloseHandle(v24, v26);
    v23 = LastError;
    goto LABEL_27;
  }
  v29 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v24, &v30);
  LastError = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v29, v30);
    goto LABEL_24;
  }
  if ( v24 )
    wil::details::CloseHandle(v24, v28);
  *a3 = v31 | (unsigned __int64)((__int64)v30 << 31);
  wil::details::CloseHandle(v19, v28);
  return 0;
}

```

## disassembly

```asm
0x180062000  mov     [rsp-8+arg_0], rbx
0x180062005  mov     [rsp-8+arg_8], rsi
0x18006200a  push    rbp
0x18006200b  push    rdi
0x18006200c  push    r12
0x18006200e  push    r14
0x180062010  push    r15
0x180062012  lea     rbp, [rsp-150h]
0x18006201a  sub     rsp, 250h
0x180062021  mov     rax, cs:__security_cookie
0x180062028  xor     rax, rsp
0x18006202b  mov     [rbp+170h+var_30], rax
0x180062032  xor     r15d, r15d
0x180062035  lea     rax, [rsp+270h+Name]
0x18006203a  mov     r10d, 7FFFFFFEh
0x180062040  mov     [r8], r15
0x180062043  mov     r12d, 104h
0x180062049  mov     r9d, r10d
0x18006204c  mov     edx, r12d
0x18006204f  mov     r14, r8
0x180062052  test    r9, r9
0x180062055  jz      short loc_180062076
0x180062057  movzx   r8d, word ptr [rcx]
0x18006205b  test    r8w, r8w
0x18006205f  jz      short loc_180062076
0x180062061  mov     [rax], r8w
0x180062065  add     rcx, 2
0x180062069  add     rax, 2
0x18006206d  dec     r9
0x180062070  sub     rdx, 1
0x180062074  jnz     short loc_180062052
0x180062076  test    rdx, rdx
0x180062079  lea     rcx, [rax-2]
0x18006207d  mov     rdx, r12
0x180062080  cmovnz  rcx, rax
0x180062084  lea     rax, [rsp+270h+Name]
0x180062089  mov     [rcx], r15w
0x18006208d  cmp     [rax], r15w
0x180062091  jz      short loc_18006209D
0x180062093  add     rax, 2
0x180062097  sub     rdx, 1
0x18006209b  jnz     short loc_18006208D
0x18006209d  mov     rcx, r12
0x1800620a0  mov     rax, rdx
0x1800620a3  sub     rcx, rdx
0x1800620a6  neg     rax
0x1800620a9  sbb     r8, r8
0x1800620ac  and     r8, rcx
0x1800620af  test    rdx, rdx
0x1800620b2  jz      short loc_1800620FF
0x1800620b4  mov     rax, r12
0x1800620b7  lea     rdx, [rsp+270h+Name]
0x1800620bc  lea     rcx, aP0; "_p0"
0x1800620c3  lea     rdx, [rdx+r8*2]
0x1800620c7  sub     rax, r8
0x1800620ca  jz      short loc_1800620F0
0x1800620cc  test    r10, r10
0x1800620cf  jz      short loc_1800620F0
0x1800620d1  movzx   r8d, word ptr [rcx]
0x1800620d5  test    r8w, r8w
0x1800620d9  jz      short loc_1800620F0
0x1800620db  mov     [rdx], r8w
0x1800620df  add     rcx, 2
0x1800620e3  add     rdx, 2
0x1800620e7  dec     r10
0x1800620ea  sub     rax, 1
0x1800620ee  jnz     short loc_1800620CC
0x1800620f0  test    rax, rax
0x1800620f3  lea     rcx, [rdx-2]
0x1800620f7  cmovnz  rcx, rdx
0x1800620fb  mov     [rcx], r15w
0x1800620ff  mov     esi, 1F0003h
0x180062104  lea     r8, [rsp+270h+Name]; lpName
0x180062109  mov     ecx, esi; dwDesiredAccess
0x18006210b  xor     edx, edx; bInheritHandle
0x18006210d  call    cs:__imp_OpenSemaphoreW
0x180062113  mov     rdi, rax
0x180062116  test    rax, rax
0x180062119  jnz     short loc_18006216D
0x18006211b  call    cs:__imp_GetLastError
0x180062121  cmp     eax, 2
0x180062124  jz      loc_18006221F
0x18006212a  mov     rcx, [rbp+178h]; this
0x180062131  lea     r8, aWil; "wil"
0x180062138  mov     edx, 0D0h; void *
0x18006213d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180062142  mov     rcx, [rbp+170h+var_30]
0x180062149  xor     rcx, rsp; StackCookie
0x18006214c  call    __security_check_cookie
0x180062151  lea     r11, [rsp+270h+var_20]
0x180062159  mov     rbx, [r11+30h]
0x18006215d  mov     rsi, [r11+38h]
0x180062161  mov     rsp, r11
0x180062164  pop     r15
0x180062166  pop     r14
0x180062168  pop     r12
0x18006216a  pop     rdi
0x18006216b  pop     rbp
0x18006216c  retn
0x18006216d  lea     rdx, [rsp+270h+var_24C]; int *
0x180062172  mov     [rsp+270h+var_24C], r15d
0x180062177  mov     rcx, rdi; hHandle
0x18006217a  mov     [rsp+270h+var_250], r15d; int
0x18006217f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180062184  mov     ebx, eax
0x180062186  test    eax, eax
0x180062188  js      loc_180062235
0x18006218e  lea     r8, asc_1800F8444; "h"
0x180062195  mov     rdx, r12; unsigned __int64
0x180062198  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18006219d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800621a2  lea     r8, [rsp+270h+Name]; lpName
0x1800621a7  xor     edx, edx; bInheritHandle
0x1800621a9  mov     ecx, esi; dwDesiredAccess
0x1800621ab  call    cs:__imp_OpenSemaphoreW
0x1800621b1  lea     rcx, [rsp+270h+var_248]
0x1800621b6  mov     [rsp+270h+var_248], rax
0x1800621bb  mov     rbx, rax
0x1800621be  call    ??$?8VCCachedBorderBrush@CWindowBorder@@@std@@YA_NAEBV?$shared_ptr@VCCachedBorderBrush@CWindowBorder@@@0@$$T@Z; std::operator==<CWindowBorder::CCachedBorderBrush>(std::shared_ptr<CWindowBorder::CCachedBorderBrush> const &,std::nullptr_t)
0x1800621c3  test    al, al
0x1800621c5  jz      loc_180062252
0x1800621cb  mov     rcx, [rbp+178h]; this
0x1800621d2  lea     r8, aWil; "wil"
0x1800621d9  mov     edx, 0DCh; void *
0x1800621de  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800621e3  mov     esi, eax
0x1800621e5  test    rbx, rbx
0x1800621e8  jz      short loc_1800621F2
0x1800621ea  mov     rcx, rbx; this
0x1800621ed  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800621f2  mov     ebx, esi
0x1800621f4  mov     rcx, rdi; this
0x1800621f7  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800621fc  mov     eax, ebx
0x1800621fe  jmp     loc_180062142
0x180062203  movsxd  rax, [rsp+270h+var_24C]
0x180062208  movsxd  rcx, [rsp+270h+var_250]
0x18006220d  shl     rcx, 1Fh
0x180062211  or      rcx, rax
0x180062214  mov     [r14], rcx
0x180062217  mov     rcx, rdi; this
0x18006221a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18006221f  xor     eax, eax
0x180062221  jmp     loc_180062142
0x180062226  test    rbx, rbx
0x180062229  jz      short loc_180062203
0x18006222b  mov     rcx, rbx; this
0x18006222e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180062233  jmp     short loc_180062203
0x180062235  mov     rcx, [rbp+178h]; this
0x18006223c  lea     r8, aWil; "wil"
0x180062243  mov     r9d, eax; char *
0x180062246  mov     edx, 0D6h; void *
0x18006224b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062250  jmp     short loc_1800621F4
0x180062252  lea     rdx, [rsp+270h+var_250]; int *
0x180062257  mov     rcx, rbx; hHandle
0x18006225a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18006225f  mov     esi, eax
0x180062261  test    eax, eax
0x180062263  jns     short loc_180062226
0x180062265  mov     rcx, [rbp+178h]; this
0x18006226c  lea     r8, aWil; "wil"
0x180062273  mov     r9d, eax; char *
0x180062276  mov     edx, 0DEh; void *
0x18006227b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062280  jmp     loc_1800621E5
```
