# CLogonEnumUsers::create(ushort *,tagVARIANT,ILogonUser * *)

- ea: `0x180033bd0`
- end: `0x180033eb9`
- name: `?create@CLogonEnumUsers@@UEAAJPEAGUtagVARIANT@@PEAPEAUILogonUser@@@Z`
- size: `745`
- prototype: `int(CLogonEnumUsers *__hidden this, unsigned __int16 *, struct tagVARIANT *__struct_ptr, struct ILogonUser **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180006f2c`
- `0x18002c814`
- `0x180032248`
- `0x180033bd0`
- `0x1800639c0`
- `0x180063b30`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033e85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033e85`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e32`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180033e32`
- `samcli!NetLocalGroupAddMembers` at `0x180033d87`
- `samcli!NetLocalGroupAddMembers` at `0x180033d87`
- `samcli!NetUserAdd` at `0x180033d03`
- `samcli!NetUserAdd` at `0x180033d2e`
- `samcli!NetUserAdd` at `0x180033d03`
- `samcli!NetUserAdd` at `0x180033d2e`
- `samcli!NetUserGetInfo` at `0x180033dc4`
- `samcli!NetUserGetInfo` at `0x180033dc4`
- `samcli!NetUserSetInfo` at `0x180033def`
- `samcli!NetUserSetInfo` at `0x180033def`
- `netutils!NetApiBufferFree` at `0x180033dfa`
- `netutils!NetApiBufferFree` at `0x180033dfa`
- `KERNEL32!GetComputerNameW` at `0x180033ca2`
- `KERNEL32!GetComputerNameW` at `0x180033ca2`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180033e90`
- `SHCORE!__imp_SHGlobalCounterIncrement` at `0x180033e90`

## pseudocode

```c
__int64 __fastcall CLogonEnumUsers::create(
        CLogonEnumUsers *this,
        unsigned __int16 *a2,
        struct tagVARIANT *a3,
        struct ILogonUser **a4)
{
  __int64 v5; // rdx
  LONGLONG llVal; // rdi
  __int64 v9; // rax
  WCHAR *v10; // r8
  WCHAR *v11; // rcx
  WCHAR *v12; // rcx
  signed int v13; // ebx
  bool v14; // sf
  signed int v15; // eax
  struct _DPA *v16; // rcx
  struct _DPA *v17; // rcx
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  LPBYTE bufptr; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v21[8]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE buf[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v23; // [rsp+58h] [rbp-A8h]
  __int128 v24; // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[256]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v27[520]; // [rsp+280h] [rbp+180h] BYREF

  v25 = 0;
  *a4 = 0;
  v5 = 256;
  nSize = 256;
  *(_OWORD *)buf = 0;
  v23 = 0;
  v24 = 0;
  if ( a3->vt != 8 )
  {
    llVal = 0;
LABEL_12:
    if ( !GetComputerNameW(Buffer, &nSize) )
      Buffer[0] = 0;
LABEL_14:
    v13 = StringCchPrintfW(v27, 0x201u, L"%s\\%s", Buffer, a2);
    if ( v13 < 0 )
      return (unsigned int)v13;
    if ( llVal )
    {
      v13 = RemoveFromLocalGroups(v27, 0);
    }
    else
    {
      *(_QWORD *)buf = a2;
      DWORD1(v23) = 1;
      DWORD2(v24) = 66049;
      v13 = NetUserAdd(0, 1u, buf, 0);
      if ( v13 == 2245 )
      {
        DWORD2(v24) = DWORD2(v24) & 0xFFFEFFDF | 0x20;
        v13 = NetUserAdd(0, 1u, buf, 0);
      }
      v14 = v13 < 0;
      if ( !v13 )
      {
LABEL_24:
        *(_QWORD *)v21 = v27;
        v15 = NetLocalGroupAddMembers(0, groupname, 3u, v21, 1u);
        v13 = v15;
        if ( !v15 )
          goto LABEL_41;
        if ( v15 > 0 )
          v13 = (unsigned __int16)v15 | 0x80070000;
        if ( v13 >= 0 )
        {
LABEL_41:
          if ( (BYTE8(v24) & 0x20) != 0 )
          {
            bufptr = 0;
            if ( !NetUserGetInfo(0, a2, 4u, &bufptr) )
            {
              *((_DWORD *)bufptr + 46) = 1;
              NetUserSetInfo(0, a2, 4u, bufptr, 0);
              NetApiBufferFree(bufptr);
            }
          }
          v13 = CLogonUser::Create(
                  a2,
                  &Class,
                  Buffer,
                  0xFFFFFFFF,
                  &GUID_01c8ac33_bdcd_401b_a7d8_e680f4da87ff,
                  (void **)a4);
          if ( v13 >= 0 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
            v16 = (struct _DPA *)*((_QWORD *)this + 5);
            if ( !v16 || DPA_InsertPtr(v16, 0x7FFFFFFF, *a4) == -1 )
            {
              v17 = (struct _DPA *)_InterlockedExchange64((volatile __int64 *)this + 5, 0);
              if ( v17 )
                g_pfn_DPA_DestroyCallback(v17, ReleaseLogonUserCallback, 0);
            }
            else
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a4 + 8LL))(*a4);
            }
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
            SHGlobalCounterIncrement(GLOBALCOUNTER_INTERNETTOOLBAR_LAYOUT|GLOBALCOUNTER_OVERLAYMANAGER);
          }
        }
        return (unsigned int)v13;
      }
      if ( v13 <= 0 )
      {
LABEL_23:
        if ( v14 )
          return (unsigned int)v13;
        goto LABEL_24;
      }
      v13 = (unsigned __int16)v13 | 0x80070000;
    }
    v14 = v13 < 0;
    goto LABEL_23;
  }
  llVal = a3->llVal;
  if ( !llVal )
    goto LABEL_12;
  v9 = 2147483646;
  v10 = Buffer;
  v11 = (WCHAR *)llVal;
  do
  {
    if ( !v9 )
      break;
    if ( !*v11 )
      break;
    *v10++ = *v11++;
    --v9;
    --v5;
  }
  while ( v5 );
  v12 = v10 - 1;
  v13 = v5 == 0 ? 0x8007007A : 0;
  if ( v5 )
    v12 = v10;
  *v12 = 0;
  if ( v5 )
    goto LABEL_14;
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180033bd0  push    rbp
0x180033bd2  push    rbx
0x180033bd3  push    rsi
0x180033bd4  push    rdi
0x180033bd5  push    r12
0x180033bd7  push    r14
0x180033bd9  push    r15
0x180033bdb  lea     rbp, [rsp-5A0h]
0x180033be3  sub     rsp, 6A0h
0x180033bea  mov     rax, cs:__security_cookie
0x180033bf1  xor     rax, rsp
0x180033bf4  mov     [rbp+5D0h+var_40], rax
0x180033bfb  xor     r12d, r12d
0x180033bfe  xor     eax, eax
0x180033c00  xorps   xmm0, xmm0
0x180033c03  mov     [rsp+6D0h+var_658], rax
0x180033c08  mov     r14, rdx
0x180033c0b  mov     [r9], r12
0x180033c0e  mov     edx, 100h
0x180033c13  mov     r15, r9
0x180033c16  lea     eax, [r12+8]
0x180033c1b  mov     [rsp+6D0h+nSize], edx
0x180033c1f  mov     rsi, rcx
0x180033c22  movups  xmmword ptr [rsp+6D0h+buf], xmm0
0x180033c27  movups  [rsp+6D0h+var_678], xmm0
0x180033c2c  movups  [rsp+6D0h+var_668], xmm0
0x180033c31  cmp     ax, [r8]
0x180033c35  jnz     short loc_180033C96
0x180033c37  mov     rdi, [r8+8]
0x180033c3b  test    rdi, rdi
0x180033c3e  jz      short loc_180033C99
0x180033c40  mov     eax, 7FFFFFFEh
0x180033c45  lea     r8, [rbp+5D0h+Buffer]
0x180033c49  mov     rcx, rdi
0x180033c4c  test    rax, rax
0x180033c4f  jz      short loc_180033C70
0x180033c51  movzx   r9d, word ptr [rcx]
0x180033c55  test    r9w, r9w
0x180033c59  jz      short loc_180033C70
0x180033c5b  mov     [r8], r9w
0x180033c5f  add     rcx, 2
0x180033c63  add     r8, 2
0x180033c67  dec     rax
0x180033c6a  sub     rdx, 1
0x180033c6e  jnz     short loc_180033C4C
0x180033c70  mov     rax, rdx
0x180033c73  lea     rcx, [r8-2]
0x180033c77  neg     rax
0x180033c7a  sbb     ebx, ebx
0x180033c7c  not     ebx
0x180033c7e  and     ebx, 8007007Ah
0x180033c84  test    rdx, rdx
0x180033c87  cmovnz  rcx, r8
0x180033c8b  mov     [rcx], r12w
0x180033c8f  jnz     short loc_180033CB1
0x180033c91  jmp     loc_180033E96
0x180033c96  mov     rdi, r12
0x180033c99  lea     rdx, [rsp+6D0h+nSize]; nSize
0x180033c9e  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x180033ca2  call    cs:__imp_GetComputerNameW
0x180033ca8  test    eax, eax
0x180033caa  jnz     short loc_180033CB1
0x180033cac  mov     [rbp+5D0h+Buffer], r12w
0x180033cb1  lea     r9, [rbp+5D0h+Buffer]
0x180033cb5  mov     qword ptr [rsp+6D0h+totalentries], r14
0x180033cba  lea     r8, aSS; "%s\\%s"
0x180033cc1  mov     edx, 201h; unsigned __int64
0x180033cc6  lea     rcx, [rbp+5D0h+var_450]; unsigned __int16 *
0x180033ccd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033cd2  mov     ebx, eax
0x180033cd4  test    eax, eax
0x180033cd6  js      loc_180033E96
0x180033cdc  test    rdi, rdi
0x180033cdf  jnz     short loc_180033D47
0x180033ce1  xor     r9d, r9d; parm_err
0x180033ce4  mov     qword ptr [rsp+6D0h+buf], r14
0x180033ce9  lea     r8, [rsp+6D0h+buf]; buf
0x180033cee  mov     dword ptr [rsp+6D0h+var_678+4], 1
0x180033cf6  lea     edx, [rdi+1]; level
0x180033cf9  mov     dword ptr [rsp+6D0h+var_668+8], 10201h
0x180033d01  xor     ecx, ecx; servername
0x180033d03  call    cs:__imp_NetUserAdd
0x180033d09  mov     ebx, eax
0x180033d0b  cmp     eax, 8C5h
0x180033d10  jnz     short loc_180033D36
0x180033d12  mov     eax, dword ptr [rsp+6D0h+var_668+8]
0x180033d16  lea     r8, [rsp+6D0h+buf]; buf
0x180033d1b  btr     eax, 10h
0x180033d1f  lea     edx, [rdi+1]; level
0x180033d22  or      eax, 20h
0x180033d25  xor     r9d, r9d; parm_err
0x180033d28  xor     ecx, ecx; servername
0x180033d2a  mov     dword ptr [rsp+6D0h+var_668+8], eax
0x180033d2e  call    cs:__imp_NetUserAdd
0x180033d34  mov     ebx, eax
0x180033d36  test    ebx, ebx
0x180033d38  jz      short loc_180033D5F
0x180033d3a  jle     short loc_180033D59
0x180033d3c  movzx   ebx, bx
0x180033d3f  or      ebx, 80070000h
0x180033d45  jmp     short loc_180033D57
0x180033d47  xor     edx, edx; unsigned __int16 *
0x180033d49  lea     rcx, [rbp+5D0h+var_450]; unsigned __int16 *
0x180033d50  call    ?RemoveFromLocalGroups@@YAJPEBG0@Z; RemoveFromLocalGroups(ushort const *,ushort const *)
0x180033d55  mov     ebx, eax
0x180033d57  test    ebx, ebx
0x180033d59  js      loc_180033E96
0x180033d5f  mov     rdx, cs:groupname; groupname
0x180033d66  lea     rax, [rbp+5D0h+var_450]
0x180033d6d  lea     r9, [rsp+6D0h+var_690]; buf
0x180033d72  mov     qword ptr [rsp+6D0h+var_690], rax
0x180033d77  mov     r8d, 3; level
0x180033d7d  mov     [rsp+6D0h+totalentries], 1; totalentries
0x180033d85  xor     ecx, ecx; servername
0x180033d87  call    cs:__imp_NetLocalGroupAddMembers
0x180033d8d  mov     ebx, eax
0x180033d8f  test    eax, eax
0x180033d91  jz      short loc_180033DA6
0x180033d93  jle     short loc_180033D9E
0x180033d95  movzx   ebx, ax
0x180033d98  or      ebx, 80070000h
0x180033d9e  test    ebx, ebx
0x180033da0  js      loc_180033E96
0x180033da6  test    byte ptr [rsp+6D0h+var_668+8], 20h
0x180033dab  jz      short loc_180033E00
0x180033dad  mov     ebx, 4
0x180033db2  mov     [rsp+6D0h+bufptr], r12
0x180033db7  mov     r8d, ebx; level
0x180033dba  lea     r9, [rsp+6D0h+bufptr]; bufptr
0x180033dbf  mov     rdx, r14; username
0x180033dc2  xor     ecx, ecx; servername
0x180033dc4  call    cs:__imp_NetUserGetInfo
0x180033dca  test    eax, eax
0x180033dcc  jnz     short loc_180033E00
0x180033dce  mov     rax, [rsp+6D0h+bufptr]
0x180033dd3  mov     r8d, ebx; level
0x180033dd6  mov     rdx, r14; username
0x180033dd9  mov     qword ptr [rsp+6D0h+totalentries], r12; parm_err
0x180033dde  xor     ecx, ecx; servername
0x180033de0  mov     dword ptr [rax+0B8h], 1
0x180033dea  mov     r9, [rsp+6D0h+bufptr]; buf
0x180033def  call    cs:__imp_NetUserSetInfo
0x180033df5  mov     rcx, [rsp+6D0h+bufptr]; Buffer
0x180033dfa  call    cs:__imp_NetApiBufferFree
0x180033e00  lea     rax, _GUID_01c8ac33_bdcd_401b_a7d8_e680f4da87ff
0x180033e07  mov     [rsp+6D0h+var_6A8], r15; void **
0x180033e0c  or      r9d, 0FFFFFFFFh; unsigned int
0x180033e10  mov     qword ptr [rsp+6D0h+totalentries], rax; struct _GUID *
0x180033e15  lea     r8, [rbp+5D0h+Buffer]; unsigned __int16 *
0x180033e19  mov     rcx, r14; unsigned __int16 *
0x180033e1c  lea     rdx, Class; unsigned __int16 *
0x180033e23  call    ?Create@CLogonUser@@SAJPEBG00KAEBU_GUID@@PEAPEAX@Z; CLogonUser::Create(ushort const *,ushort const *,ushort const *,ulong,_GUID const &,void * *)
0x180033e28  mov     ebx, eax
0x180033e2a  test    eax, eax
0x180033e2c  js      short loc_180033E96
0x180033e2e  lea     rcx, [rsi+30h]; lpCriticalSection
0x180033e32  call    cs:__imp_EnterCriticalSection
0x180033e38  mov     rcx, [rsi+28h]; hdpa
0x180033e3c  test    rcx, rcx
0x180033e3f  jz      short loc_180033E65
0x180033e41  mov     r8, [r15]; p
0x180033e44  mov     edx, 7FFFFFFFh; i
0x180033e49  call    cs:__imp_DPA_InsertPtr
0x180033e4f  cmp     eax, 0FFFFFFFFh
0x180033e52  jz      short loc_180033E65
0x180033e54  mov     rcx, [r15]
0x180033e57  mov     rax, [rcx]
0x180033e5a  mov     rax, [rax+8]
0x180033e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e63  jmp     short loc_180033E81
0x180033e65  mov     rcx, r12
0x180033e68  xchg    rcx, [rsi+28h]; hdpa
0x180033e6c  test    rcx, rcx
0x180033e6f  jz      short loc_180033E81
0x180033e71  xor     r8d, r8d; pData
0x180033e74  lea     rdx, ReleaseLogonUserCallback; pfnCB
0x180033e7b  call    cs:g_pfn_DPA_DestroyCallback
0x180033e81  lea     rcx, [rsi+30h]; lpCriticalSection
0x180033e85  call    cs:__imp_LeaveCriticalSection
0x180033e8b  mov     ecx, 38h ; '8'; id
0x180033e90  call    cs:__imp_SHGlobalCounterIncrement
0x180033e96  mov     eax, ebx
0x180033e98  mov     rcx, [rbp+5D0h+var_40]
0x180033e9f  xor     rcx, rsp; StackCookie
0x180033ea2  call    __security_check_cookie
0x180033ea7  add     rsp, 6A0h
0x180033eae  pop     r15
0x180033eb0  pop     r14
0x180033eb2  pop     r12
0x180033eb4  pop     rdi
0x180033eb5  pop     rsi
0x180033eb6  pop     rbx
0x180033eb7  pop     rbp
0x180033eb8  retn
```
