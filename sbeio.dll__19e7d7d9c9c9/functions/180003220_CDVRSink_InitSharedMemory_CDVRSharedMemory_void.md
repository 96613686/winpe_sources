# CDVRSink::InitSharedMemory(CDVRSharedMemory *,void * &)

- ea: `0x180003220`
- end: `0x180003431`
- name: `?InitSharedMemory@CDVRSink@@MEAAJPEAUCDVRSharedMemory@@AEAPEAX@Z`
- size: `529`
- prototype: `int(CDVRSink *__hidden this, struct CDVRSharedMemory *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800015f0`
- `0x180001f1c`
- `0x1800024c4`
- `0x1800027c4`
- `0x180003220`
- `0x1800050cc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800033ac`
- `KERNEL32!GetCurrentProcessId` at `0x1800033ac`
- `KERNEL32!CloseHandle` at `0x180003395`
- `KERNEL32!CloseHandle` at `0x180003395`
- `KERNEL32!GetLastError` at `0x18000334c`
- `KERNEL32!GetLastError` at `0x18000334c`
- `KERNEL32!CreateMutexW` at `0x180003343`
- `KERNEL32!CreateMutexW` at `0x180003343`

## pseudocode

```c
__int64 __fastcall CDVRSink::InitSharedMemory(CDVRSink *this, struct CDVRSharedMemory *a2, void **a3)
{
  enum _ACCESS_MODE v6; // r8d
  ULONG v7; // ecx
  __int64 result; // rax
  int i; // ebx
  struct _SECURITY_ATTRIBUTES *v10; // rcx
  HANDLE MutexW; // r14
  DWORD LastError; // eax
  __int64 j; // rdx
  __int64 v14; // [rsp+20h] [rbp-298h]
  void *v15; // [rsp+48h] [rbp-270h] BYREF
  struct _ACL *v16; // [rsp+50h] [rbp-268h] BYREF
  __int128 v17; // [rsp+58h] [rbp-260h] BYREF
  __int64 v18; // [rsp+68h] [rbp-250h]
  WCHAR Name[264]; // [rsp+70h] [rbp-248h] BYREF

  memset_0(a2, 0, 0x1F8u);
  *a3 = 0;
  v16 = 0;
  v15 = 0;
  v17 = 0;
  v18 = 0;
  v7 = *((_DWORD *)this + 2441);
  if ( v7 )
  {
    result = CreateACL(v7, *((void ***)this + 1222), v6, 2031617, (enum _ACCESS_MODE)v14, 0x100000u, &v16, &v15);
    if ( (_DWORD)result )
    {
      if ( (int)result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    LODWORD(v17) = 24;
    *((_QWORD *)&v17 + 1) = v15;
    LODWORD(v18) = 0;
  }
  for ( i = 1; i != -1; ++i )
  {
    LODWORD(v14) = i;
    result = StringCchPrintfW(Name, 0x104u, L"%s%u", L"Global\\_MS_TSDVRASF_MUTEX_", v14);
    if ( (int)result < 0 )
      return result;
    v10 = (struct _SECURITY_ATTRIBUTES *)&v17;
    if ( !*((_DWORD *)this + 2441) )
      v10 = 0;
    MutexW = CreateMutexW(v10, 1, Name);
    LastError = GetLastError();
    if ( MutexW )
    {
      if ( LastError != 183 )
      {
        *((_DWORD *)a2 + 96) = i;
        *a3 = MutexW;
        break;
      }
      CloseHandle(MutexW);
    }
  }
  if ( *((_DWORD *)this + 2441) )
    FreeSecurityDescriptors(&v16, &v15);
  if ( !i )
    return 2147500037LL;
  *((_DWORD *)a2 + 104) = 1;
  *((_DWORD *)a2 + 101) = GetCurrentProcessId();
  *(_OWORD *)a2 = *((_OWORD *)this + 582);
  *((_DWORD *)a2 + 102) = 1;
  *((_DWORD *)a2 + 103) = *((_DWORD *)this + 2342);
  *((_QWORD *)a2 + 4) = 0xFFFFFFFF00000000uLL;
  *((_QWORD *)a2 + 5) = 0xFFFFFFFF00000000uLL;
  *((_QWORD *)a2 + 6) = 0xFFFFFFFF00000000uLL;
  *((_QWORD *)a2 + 7) = 0xFFFFFFFF00000000uLL;
  for ( j = 0; (unsigned int)j < 8; j = (unsigned int)(j + 1) )
    *((_DWORD *)a2 + 10 * j + 19) = 0;
  return 0;
}

```

## disassembly

```asm
0x180003220  push    rbx
0x180003222  push    rsi
0x180003223  push    rdi
0x180003224  push    r14
0x180003226  push    r15
0x180003228  sub     rsp, 290h
0x18000322f  mov     rax, cs:__security_cookie
0x180003236  xor     rax, rsp
0x180003239  mov     [rsp+2B8h+var_38], rax
0x180003241  mov     r15, r8
0x180003244  mov     rdi, rdx
0x180003247  mov     rsi, rcx
0x18000324a  mov     [rsp+2B8h+var_278], 0
0x180003252  xor     edx, edx; Val
0x180003254  mov     r8d, 1F8h; Size
0x18000325a  mov     rcx, rdi; void *
0x18000325d  call    memset_0
0x180003262  mov     qword ptr [r15], 0
0x180003269  mov     [rsp+2B8h+var_268], 0
0x180003272  mov     [rsp+2B8h+var_270], 0
0x18000327b  xorps   xmm0, xmm0
0x18000327e  xor     eax, eax
0x180003280  movups  [rsp+2B8h+var_260], xmm0
0x180003285  mov     [rsp+2B8h+var_250], rax
0x18000328a  mov     ecx, [rsi+2624h]; cCountOfExplicitEntries
0x180003290  test    ecx, ecx
0x180003292  jz      short loc_1800032F3
0x180003294  lea     rax, [rsp+2B8h+var_270]
0x180003299  mov     [rsp+2B8h+var_280], rax; void **
0x18000329e  lea     rax, [rsp+2B8h+var_268]
0x1800032a3  mov     [rsp+2B8h+var_288], rax; struct _ACL **
0x1800032a8  mov     [rsp+2B8h+var_290], 100000h; unsigned int
0x1800032b0  mov     r9d, 1F0001h; unsigned int
0x1800032b6  mov     rdx, [rsi+2630h]; void **
0x1800032bd  call    ?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z; CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)
0x1800032c2  test    eax, eax
0x1800032c4  jz      short loc_1800032D9
0x1800032c6  jle     loc_180003412
0x1800032cc  movzx   eax, ax
0x1800032cf  or      eax, 80070000h
0x1800032d4  jmp     loc_180003412
0x1800032d9  mov     dword ptr [rsp+2B8h+var_260], 18h
0x1800032e1  mov     rax, [rsp+2B8h+var_270]
0x1800032e6  mov     qword ptr [rsp+2B8h+var_260+8], rax
0x1800032eb  mov     dword ptr [rsp+2B8h+var_250], 0
0x1800032f3  mov     ebx, 1
0x1800032f8  mov     [rsp+2B8h+var_278], ebx
0x1800032fc  cmp     ebx, 0FFFFFFFFh
0x1800032ff  jnb     short loc_180003367
0x180003301  mov     dword ptr [rsp+2B8h+var_298], ebx
0x180003305  lea     r9, aGlobalMsTsdvra; "Global\\_MS_TSDVRASF_MUTEX_"
0x18000330c  lea     r8, aSU; "%s%u"
0x180003313  mov     edx, 104h; unsigned __int64
0x180003318  lea     rcx, [rsp+2B8h+Name]; unsigned __int16 *
0x18000331d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003322  test    eax, eax
0x180003324  js      loc_180003412
0x18000332a  lea     rcx, [rsp+2B8h+var_260]
0x18000332f  xor     eax, eax
0x180003331  cmp     [rsi+2624h], eax
0x180003337  cmovbe  rcx, rax; lpMutexAttributes
0x18000333b  lea     r8, [rsp+2B8h+Name]; lpName
0x180003340  lea     edx, [rax+1]; bInitialOwner
0x180003343  call    cs:__imp_CreateMutexW
0x180003349  mov     r14, rax
0x18000334c  call    cs:__imp_GetLastError
0x180003352  test    r14, r14
0x180003355  jz      short loc_18000339B
0x180003357  cmp     eax, 0B7h
0x18000335c  jz      short loc_18000338D
0x18000335e  mov     [rdi+180h], ebx
0x180003364  mov     [r15], r14
0x180003367  cmp     dword ptr [rsi+2624h], 0
0x18000336e  jbe     short loc_18000337F
0x180003370  lea     rdx, [rsp+2B8h+var_270]; void **
0x180003375  lea     rcx, [rsp+2B8h+var_268]; struct _ACL **
0x18000337a  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x18000337f  test    ebx, ebx
0x180003381  jnz     short loc_1800033A2
0x180003383  mov     eax, 80004005h
0x180003388  jmp     loc_180003412
0x18000338d  test    r14, r14
0x180003390  jz      short loc_18000339B
0x180003392  mov     rcx, r14; hObject
0x180003395  call    cs:__imp_CloseHandle
0x18000339b  inc     ebx
0x18000339d  jmp     loc_1800032F8
0x1800033a2  mov     dword ptr [rdi+1A0h], 1
0x1800033ac  call    cs:__imp_GetCurrentProcessId
0x1800033b2  mov     [rdi+194h], eax
0x1800033b8  movups  xmm0, xmmword ptr [rsi+2460h]
0x1800033bf  movdqu  xmmword ptr [rdi], xmm0
0x1800033c3  mov     dword ptr [rdi+198h], 1
0x1800033cd  mov     eax, [rsi+2498h]
0x1800033d3  mov     [rdi+19Ch], eax
0x1800033d9  mov     rax, 0FFFFFFFF00000000h
0x1800033e3  mov     [rdi+20h], rax
0x1800033e7  mov     [rdi+28h], rax
0x1800033eb  mov     [rdi+30h], rax
0x1800033ef  mov     [rdi+38h], rax
0x1800033f3  xor     edx, edx
0x1800033f5  mov     [rsp+2B8h+var_278], edx
0x1800033f9  cmp     edx, 8
0x1800033fc  jnb     short loc_180003410
0x1800033fe  mov     eax, edx
0x180003400  lea     rcx, [rdx+rdx*4]
0x180003404  mov     dword ptr [rdi+rcx*8+4Ch], 0
0x18000340c  inc     edx
0x18000340e  jmp     short loc_1800033F5
0x180003410  xor     eax, eax
0x180003412  mov     rcx, [rsp+2B8h+var_38]
0x18000341a  xor     rcx, rsp; StackCookie
0x18000341d  call    __security_check_cookie
0x180003422  add     rsp, 290h
0x180003429  pop     r15
0x18000342b  pop     r14
0x18000342d  pop     rdi
0x18000342e  pop     rsi
0x18000342f  pop     rbx
0x180003430  retn
0x18002a330  push    rbp
0x18002a332  sub     rsp, 40h
0x18002a336  mov     rbp, rdx
0x18002a339  add     rsp, 40h
0x18002a33d  pop     rbp
0x18002a33e  retn
```
