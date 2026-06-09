# CLogonEnumUsers::_GetUserByDomainAndName(ushort const *,ushort const *,ILogonUser * *)

- ea: `0x180033318`
- end: `0x1800334b1`
- name: `?_GetUserByDomainAndName@CLogonEnumUsers@@AEAAJPEBG0PEAPEAUILogonUser@@@Z`
- size: `409`
- prototype: `__int64 __fastcall(CLogonEnumUsers *__hidden this, LPCWCH lpString1, const unsigned __int16 *, struct ILogonUser **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180033ec0`
- `0x180034250`

## callees

- `0x180032dd4`
- `0x180033318`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003348f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003348f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033392`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033392`
- `OLEAUT32!__imp_SysAllocString` at `0x18003337c`
- `OLEAUT32!__imp_SysAllocString` at `0x18003337c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003343c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033447`
- `OLEAUT32!__imp_SysFreeString` at `0x180033498`
- `OLEAUT32!__imp_SysFreeString` at `0x18003343c`
- `OLEAUT32!__imp_SysFreeString` at `0x180033447`
- `OLEAUT32!__imp_SysFreeString` at `0x180033498`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033405`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003342a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033405`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003342a`

## pseudocode

```c
__int64 __fastcall CLogonEnumUsers::_GetUserByDomainAndName(
        CLogonEnumUsers *this,
        LPCWCH lpString1,
        const unsigned __int16 *a3,
        struct ILogonUser **a4)
{
  const WCHAR *v5; // rbx
  unsigned int v6; // edi
  __int64 result; // rax
  OLECHAR *v8; // r15
  __int64 v9; // rbp
  int v10; // r13d
  struct ILogonUser *v11; // r14
  int v12; // ebx
  __int128 v13; // [rsp+30h] [rbp-78h] BYREF
  __int64 v14; // [rsp+40h] [rbp-68h]
  __int128 v15; // [rsp+48h] [rbp-60h] BYREF
  __int64 v16; // [rsp+58h] [rbp-50h]
  int v17; // [rsp+B0h] [rbp+8h]

  *a4 = 0;
  v5 = lpString1;
  v6 = -2147024882;
  v14 = 0;
  v13 = 0;
  v16 = 0;
  v15 = 0;
  if ( *((_QWORD *)this + 5) || (result = CLogonEnumUsers::_EnumerateUsers(this), v6 = result, (int)result >= 0) )
  {
    v8 = SysAllocString(L"LoginName");
    if ( v8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      v9 = 0;
      v6 = -2147024809;
      v10 = **((_DWORD **)this + 5);
      if ( v10 > 0 )
      {
        while ( 1 )
        {
          v11 = *(struct ILogonUser **)(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + 8 * v9);
          (*(void (__fastcall **)(struct ILogonUser *, OLECHAR *, __int128 *))(*(_QWORD *)v11 + 24LL))(v11, v8, &v13);
          (*(void (__fastcall **)(struct ILogonUser *, const WCHAR *, __int128 *))(*(_QWORD *)v11 + 24LL))(
            v11,
            L"Domain",
            &v15);
          v12 = CompareStringOrdinal(v5, -1, *((LPCWCH *)&v15 + 1), -1, 1);
          v17 = CompareStringOrdinal(a3, -1, *((LPCWCH *)&v13 + 1), -1, 0);
          SysFreeString(*((BSTR *)&v13 + 1));
          SysFreeString(*((BSTR *)&v15 + 1));
          if ( v12 == 2 && v17 == 2 )
            break;
          v9 = (unsigned int)(v9 + 1);
          if ( (int)v9 >= v10 )
            goto LABEL_10;
          v5 = lpString1;
        }
        *a4 = v11;
        (*(void (__fastcall **)(struct ILogonUser *))(*(_QWORD *)v11 + 8LL))(v11);
        v6 = 0;
      }
LABEL_10:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      SysFreeString(v8);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180033318  mov     rax, rsp
0x18003331b  mov     [rax+20h], r9
0x18003331f  mov     [rax+18h], r8
0x180033323  mov     [rax+10h], rdx
0x180033327  push    rbx
0x180033328  push    rbp
0x180033329  push    rsi
0x18003332a  push    rdi
0x18003332b  push    r12
0x18003332d  push    r13
0x18003332f  push    r14
0x180033331  push    r15
0x180033333  sub     rsp, 68h
0x180033337  mov     rsi, rcx
0x18003333a  xorps   xmm0, xmm0
0x18003333d  xor     ecx, ecx
0x18003333f  xorps   xmm1, xmm1
0x180033342  mov     [r9], rcx
0x180033345  mov     rbx, rdx
0x180033348  mov     edi, 8007000Eh
0x18003334d  mov     [rax-68h], rcx
0x180033351  movups  xmmword ptr [rax-78h], xmm0
0x180033355  mov     [rax-50h], rcx
0x180033359  movups  xmmword ptr [rax-60h], xmm1
0x18003335d  cmp     [rsi+28h], rcx
0x180033361  jnz     short loc_180033375
0x180033363  mov     rcx, rsi; this
0x180033366  call    ?_EnumerateUsers@CLogonEnumUsers@@AEAAJXZ; CLogonEnumUsers::_EnumerateUsers(void)
0x18003336b  mov     edi, eax
0x18003336d  test    eax, eax
0x18003336f  js      loc_1800334A0
0x180033375  lea     rcx, aLoginname_0; "LoginName"
0x18003337c  call    cs:__imp_SysAllocString
0x180033382  mov     r15, rax
0x180033385  test    rax, rax
0x180033388  jz      loc_18003349E
0x18003338e  lea     rcx, [rsi+30h]; lpCriticalSection
0x180033392  call    cs:__imp_EnterCriticalSection
0x180033398  mov     rcx, [rsi+28h]
0x18003339c  xor     ebp, ebp
0x18003339e  mov     edi, 80070057h
0x1800333a3  mov     r13d, [rcx]
0x1800333a6  test    r13d, r13d
0x1800333a9  jle     loc_18003348B
0x1800333af  mov     rax, [rsi+28h]
0x1800333b3  lea     r8, [rsp+0A8h+var_78]
0x1800333b8  mov     rdx, r15
0x1800333bb  mov     rcx, [rax+8]
0x1800333bf  mov     r14, [rcx+rbp*8]
0x1800333c3  mov     rcx, r14
0x1800333c6  mov     rax, [r14]
0x1800333c9  mov     rax, [rax+18h]
0x1800333cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333d2  mov     rax, [r14]
0x1800333d5  lea     r8, [rsp+0A8h+var_60]
0x1800333da  lea     rdx, aDomain_0; "Domain"
0x1800333e1  mov     rcx, r14
0x1800333e4  mov     rax, [rax+18h]
0x1800333e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800333ed  mov     r8, [rsp+0A8h+lpString2]; lpString2
0x1800333f2  or      eax, 0FFFFFFFFh
0x1800333f5  mov     r9d, eax; cchCount2
0x1800333f8  mov     [rsp+0A8h+bIgnoreCase], 1; bIgnoreCase
0x180033400  mov     edx, eax; cchCount1
0x180033402  mov     rcx, rbx; lpString1
0x180033405  call    cs:__imp_CompareStringOrdinal
0x18003340b  mov     r8, [rsp+0A8h+var_70]; lpString2
0x180033410  mov     ebx, eax
0x180033412  mov     rcx, [rsp+0A8h+lpString1]; lpString1
0x18003341a  or      eax, 0FFFFFFFFh
0x18003341d  mov     r9d, eax; cchCount2
0x180033420  mov     [rsp+0A8h+bIgnoreCase], 0; bIgnoreCase
0x180033428  mov     edx, eax; cchCount1
0x18003342a  call    cs:__imp_CompareStringOrdinal
0x180033430  mov     rcx, [rsp+0A8h+var_70]; bstrString
0x180033435  mov     [rsp+0A8h+arg_0], eax
0x18003343c  call    cs:__imp_SysFreeString
0x180033442  mov     rcx, [rsp+0A8h+lpString2]; bstrString
0x180033447  call    cs:__imp_SysFreeString
0x18003344d  cmp     ebx, 2
0x180033450  jnz     short loc_18003345B
0x180033452  cmp     [rsp+0A8h+arg_0], ebx
0x180033459  jz      short loc_18003346F
0x18003345b  inc     ebp
0x18003345d  cmp     ebp, r13d
0x180033460  jge     short loc_18003348B
0x180033462  mov     rbx, [rsp+0A8h+arg_8]
0x18003346a  jmp     loc_1800333AF
0x18003346f  mov     rax, [rsp+0A8h+arg_18]
0x180033477  mov     rcx, r14
0x18003347a  mov     [rax], r14
0x18003347d  mov     rax, [r14]
0x180033480  mov     rax, [rax+8]
0x180033484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033489  xor     edi, edi
0x18003348b  lea     rcx, [rsi+30h]; lpCriticalSection
0x18003348f  call    cs:__imp_LeaveCriticalSection
0x180033495  mov     rcx, r15; bstrString
0x180033498  call    cs:__imp_SysFreeString
0x18003349e  mov     eax, edi
0x1800334a0  add     rsp, 68h
0x1800334a4  pop     r15
0x1800334a6  pop     r14
0x1800334a8  pop     r13
0x1800334aa  pop     r12
0x1800334ac  pop     rdi
0x1800334ad  pop     rsi
0x1800334ae  pop     rbp
0x1800334af  pop     rbx
0x1800334b0  retn
```
