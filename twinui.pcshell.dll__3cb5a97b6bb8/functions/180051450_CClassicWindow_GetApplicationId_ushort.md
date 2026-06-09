# CClassicWindow::GetApplicationId(ushort * *)

- ea: `0x180051450`
- end: `0x180051921`
- name: `?GetApplicationId@CClassicWindow@@UEAAJPEAPEAG@Z`
- size: `1233`
- prototype: `__int64 __fastcall(CClassicWindow *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800237c8`
- `0x180051450`
- `0x180051bc0`
- `0x180052db0`
- `0x180193608`
- `0x1802dd470`
- `0x180356360`
- `0x180356dc6`
- `0x180356edc`
- `0x18035b7f1`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800518f6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800518f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005155a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800516af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800517fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005155a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800516af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800517fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005170e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051502`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005170e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051769`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051753`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180051753`
- `ntdll!NtQueryInformationProcess` at `0x1800517ae`
- `ntdll!NtQueryInformationProcess` at `0x1800517ae`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051616`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005172b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180051616`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18005172b`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180051671`
- `api-ms-win-core-atoms-l1-1-0!GlobalGetAtomNameW` at `0x180051671`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800515fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800515fc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x1800515d9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetPropW` at `0x1800515d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClassicWindow::GetApplicationId(CClassicWindow *this, unsigned __int16 **a2)
{
  char *v3; // r14
  unsigned __int64 v4; // rsi
  unsigned int v5; // r13d
  unsigned __int16 **v6; // r15
  __int16 *v7; // rbx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rdi
  unsigned __int16 *v10; // rcx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r8
  unsigned __int16 *v14; // rdx
  __int16 v15; // ax
  HWND v16; // rcx
  ATOM PropW; // ax
  char *v18; // rdi
  __int64 v19; // rax
  __int64 v20; // r12
  WCHAR *v21; // rbx
  char *v22; // rbp
  rsize_t v23; // rbx
  HANDLE v24; // rax
  unsigned __int16 **v25; // r8
  void *v26; // rbx
  int ProcessAppId; // ebp
  NTSTATUS v28; // eax
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // rax
  char *i; // rbx
  __int64 v32; // r12
  SIZE_T v33; // r15
  char *v34; // rbp
  size_t v35; // rbx
  unsigned __int16 **v36; // r8
  int ReturnLength; // [rsp+20h] [rbp-478h]
  int ReturnLengtha; // [rsp+20h] [rbp-478h]
  int ReturnLengthb; // [rsp+20h] [rbp-478h]
  DWORD dwProcessId; // [rsp+30h] [rbp-468h] BYREF
  ULONG v41[2]; // [rsp+38h] [rbp-460h] BYREF
  unsigned __int16 **v42; // [rsp+40h] [rbp-458h]
  int ProcessInformation; // [rsp+50h] [rbp-448h] BYREF
  unsigned __int16 v44; // [rsp+54h] [rbp-444h]
  _BYTE Src[506]; // [rsp+56h] [rbp-442h] BYREF
  WCHAR Buffer[256]; // [rsp+250h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+498h] [rbp+0h]

  v42 = a2;
  v3 = (char *)this + 40;
  v4 = -1;
  v5 = -2147024882;
  if ( !*((_QWORD *)this + 5) )
  {
    *((_QWORD *)this + 6) = -1;
    *((_QWORD *)this + 7) = -1;
    v16 = (HWND)*((_QWORD *)this + 2);
    *(_QWORD *)v3 = 0;
    PropW = (unsigned __int16)GetPropW(v16, L"{9F4C2855-9F79-4B39-A8D0-E1D42DE1D5F3} 5");
    if ( PropW )
    {
      LODWORD(v19) = GlobalGetAtomNameW(PropW, Buffer, 256);
      if ( (_DWORD)v19 )
      {
        v20 = (unsigned int)v19;
        v21 = Buffer;
        v19 = (unsigned int)v19;
        if ( (unsigned int)v19 >= 0x7FFFFFFF )
          v19 = 0x7FFFFFFF;
        do
        {
          if ( !*v21 )
            break;
          ++v21;
          --v19;
        }
        while ( v19 );
        v22 = (char *)CoTaskMemAlloc(2 * v20 + 2);
        if ( !v22 )
        {
          *(_QWORD *)v3 = 0;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x60,
            (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
            (const char *)0x8007000ELL,
            ReturnLength);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"pcshell\\twinui\\appmanager\\lib\\classicwndmgr.cpp",
            (const char *)0x8007000ELL,
            ReturnLengthb);
          return v5;
        }
        v23 = 2 * (v21 - Buffer);
        memcpy_s(v22, 2 * v20 + 2, Buffer, v23);
        *(_WORD *)&v22[v23] = 0;
        *(_WORD *)&v22[2 * v20] = 0;
        *(_QWORD *)v3 = v22;
      }
    }
    if ( !*(_QWORD *)v3 )
    {
      dwProcessId = 0;
      if ( GetWindowThreadProcessId(*((HWND *)this + 2), &dwProcessId) )
      {
        v18 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
        *(_QWORD *)v41 = v18;
        if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          if ( *(_QWORD *)v3 )
            CoTaskMemFree(*(LPVOID *)v3);
          *((_QWORD *)v3 + 1) = -1;
          *((_QWORD *)v3 + 2) = -1;
          *(_QWORD *)v3 = 0;
          v24 = OpenProcess(0x1000u, 0, dwProcessId);
          v26 = v24;
          if ( v24 )
          {
            ProcessAppId = CallerIdentity::GetProcessAppId(v24, (wchar_t **)v3, v25);
            if ( v26 != (void *)-1LL )
              CloseHandle(v26);
          }
          else
          {
            ProcessAppId = ResultFromLastError();
            if ( ProcessAppId >= 0 )
              ProcessAppId = CallerIdentity::GetProcessAppId(0, (wchar_t **)v3, v36);
          }
          if ( ProcessAppId < 0 )
          {
            if ( *(_QWORD *)v3 )
              CoTaskMemFree(*(LPVOID *)v3);
            *((_QWORD *)v3 + 1) = -1;
            *((_QWORD *)v3 + 2) = -1;
            *(_QWORD *)v3 = 0;
            memset_0(&ProcessInformation, 0, 0x200u);
            v41[0] = 0;
            v28 = NtQueryInformationProcess(
                    v18,
                    ProcessExecuteFlags|ProcessUserModeIOPL,
                    &ProcessInformation,
                    0x200u,
                    v41);
            if ( v28 < 0 )
            {
              wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x191,
                (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
                (const char *)(unsigned int)v28,
                ReturnLengtha);
            }
            else if ( (ProcessInformation & 0x1000) != 0 )
            {
              v29 = (unsigned __int64)v44 >> 1;
              v30 = v29;
              for ( i = Src; v30; --v30 )
              {
                if ( !*(_WORD *)i )
                  break;
                i += 2;
              }
              v32 = 2 * v29;
              v33 = 2 * v29 + 2;
              v34 = (char *)CoTaskMemAlloc(v33);
              if ( v34 )
              {
                v35 = 2 * ((i - Src) >> 1);
                if ( v35 )
                {
                  if ( v33 < v35 )
                  {
                    memset_0(v34, 0, v33);
                    *(_DWORD *)_o__errno() = 34;
                    invalid_parameter_noinfo();
                  }
                  else
                  {
                    memcpy_0(v34, Src, v35);
                  }
                }
                *(_WORD *)&v34[v35] = 0;
                *(_WORD *)&v34[v32] = 0;
                *(_QWORD *)v3 = v34;
              }
              else
              {
                *(_QWORD *)v3 = 0;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x196,
                  (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity.cpp",
                  (const char *)0x8007000ELL,
                  ReturnLengtha);
              }
            }
          }
        }
        if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v18);
      }
    }
  }
  v6 = v42;
  *v42 = 0;
  v7 = *(__int16 **)v3;
  if ( !*(_QWORD *)v3 )
    return (unsigned int)-2147023728;
  v8 = *((_QWORD *)v3 + 1);
  if ( v8 == -1 )
  {
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
  }
  do
    ++v4;
  while ( v7[v4] );
  if ( v8 == -1 )
  {
    v8 = v4;
  }
  else if ( v8 < v4 )
  {
    v4 = v8;
  }
  v9 = v8 + 1;
  if ( v8 + 1 < v8 || !is_mul_ok(v9, 2u) )
    return (unsigned int)-2147024362;
  v12 = (unsigned __int16 *)CoTaskMemAlloc(2 * v9);
  v13 = v12;
  if ( !v12 )
    return v5;
  *v12 = 0;
  if ( v9 )
  {
    if ( v9 <= 0x7FFFFFFF )
    {
      v5 = 0;
      if ( v4 > 0x7FFFFFFE )
      {
        *v12 = 0;
      }
      else
      {
        v14 = v12;
        do
        {
          if ( !v4 )
            break;
          v15 = *v7;
          if ( !*v7 )
            break;
          ++v7;
          *v14++ = v15;
          --v4;
          --v9;
        }
        while ( v9 );
        v10 = v14 - 1;
        if ( v9 )
          v10 = v14;
        *v10 = 0;
      }
      goto LABEL_16;
    }
    *v12 = 0;
  }
  v5 = 0;
LABEL_16:
  *v6 = v13;
  return v5;
}

```

## disassembly

```asm
0x180051450  mov     [rsp+arg_10], rbx
0x180051455  push    rbp
0x180051456  push    rsi
0x180051457  push    rdi
0x180051458  push    r12
0x18005145a  push    r13
0x18005145c  push    r14
0x18005145e  push    r15
0x180051460  sub     rsp, 460h
0x180051467  mov     rax, cs:__security_cookie
0x18005146e  xor     rax, rsp
0x180051471  mov     [rsp+498h+var_48], rax
0x180051479  mov     [rsp+498h+var_458], rdx
0x18005147e  mov     rdi, rcx
0x180051481  lea     r14, [rcx+28h]
0x180051485  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18005148c  mov     r13d, 8007000Eh
0x180051492  xor     r12d, r12d
0x180051495  cmp     [r14], r12
0x180051498  jz      loc_1800515C3
0x18005149e  mov     r15, [rsp+498h+var_458]
0x1800514a3  mov     [r15], r12
0x1800514a6  mov     rbx, [r14]
0x1800514a9  test    rbx, rbx
0x1800514ac  jz      loc_18005164D
0x1800514b2  mov     rax, [r14+8]
0x1800514b6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800514ba  jnz     short loc_1800514D0
0x1800514bc  mov     rax, rsi
0x1800514bf  nop
0x1800514c0  inc     rax
0x1800514c3  cmp     word ptr [rbx+rax*2], 0
0x1800514c8  jnz     short loc_1800514C0
0x1800514ca  nop     word ptr [rax+rax+00h]
0x1800514d0  inc     rsi
0x1800514d3  cmp     word ptr [rbx+rsi*2], 0
0x1800514d8  jnz     short loc_1800514D0
0x1800514da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800514de  jz      loc_180051658
0x1800514e4  cmp     rax, rsi
0x1800514e7  cmovb   rsi, rax
0x1800514eb  lea     rdi, [rax+1]
0x1800514ef  cmp     rdi, rax
0x1800514f2  jnb     short loc_18005154A
0x1800514f4  mov     r13d, 80070216h
0x1800514fa  test    r12, r12
0x1800514fd  jz      short loc_18005151C
0x1800514ff  mov     rcx, r12; pv
0x180051502  call    cs:__imp_CoTaskMemFree
0x180051508  jmp     short loc_18005151C
0x18005150a  lea     rcx, [rdx-2]
0x18005150e  test    rdi, rdi
0x180051511  cmovnz  rcx, rdx
0x180051515  mov     [rcx], r12w
0x180051519  mov     [r15], r8
0x18005151c  mov     eax, r13d
0x18005151f  mov     rcx, [rsp+498h+var_48]
0x180051527  xor     rcx, rsp; StackCookie
0x18005152a  call    __security_check_cookie
0x18005152f  mov     rbx, [rsp+498h+arg_10]
0x180051537  add     rsp, 460h
0x18005153e  pop     r15
0x180051540  pop     r14
0x180051542  pop     r13
0x180051544  pop     r12
0x180051546  pop     rdi
0x180051547  pop     rsi
0x180051548  pop     rbp
0x180051549  retn
0x18005154a  mov     eax, 2
0x18005154f  mul     rdi
0x180051552  test    rdx, rdx
0x180051555  jnz     short loc_1800514F4
0x180051557  mov     rcx, rax; cb
0x18005155a  call    cs:__imp_CoTaskMemAlloc
0x180051560  mov     r8, rax
0x180051563  test    rax, rax
0x180051566  jz      short loc_1800514FA
0x180051568  mov     [rax], r12w
0x18005156c  test    rdi, rdi
0x18005156f  jz      loc_180051910
0x180051575  cmp     rdi, 7FFFFFFFh
0x18005157c  ja      loc_18005190C
0x180051582  mov     r13d, r12d
0x180051585  cmp     rsi, 7FFFFFFEh
0x18005158c  ja      loc_180051918
0x180051592  mov     rdx, rax
0x180051595  test    rsi, rsi
0x180051598  jz      loc_18005150A
0x18005159e  movzx   eax, word ptr [rbx]
0x1800515a1  test    ax, ax
0x1800515a4  jz      loc_18005150A
0x1800515aa  add     rbx, 2
0x1800515ae  mov     [rdx], ax
0x1800515b1  add     rdx, 2
0x1800515b5  dec     rsi
0x1800515b8  sub     rdi, 1
0x1800515bc  jnz     short loc_180051595
0x1800515be  jmp     loc_18005150A
0x1800515c3  mov     [r14+8], rsi
0x1800515c7  mov     [r14+10h], rsi
0x1800515cb  mov     rcx, [rcx+10h]; hWnd
0x1800515cf  mov     [r14], r12
0x1800515d2  lea     rdx, a9f4c28559f794b; "{9F4C2855-9F79-4B39-A8D0-E1D42DE1D5F3} "...
0x1800515d9  call    cs:__imp_GetPropW
0x1800515df  test    ax, ax
0x1800515e2  jnz     short loc_180051660
0x1800515e4  cmp     qword ptr [r14], 0
0x1800515e8  jnz     loc_18005149E
0x1800515ee  mov     [rsp+498h+dwProcessId], r12d
0x1800515f3  lea     rdx, [rsp+498h+dwProcessId]; lpdwProcessId
0x1800515f8  mov     rcx, [rdi+10h]; hWnd
0x1800515fc  call    cs:__imp_GetWindowThreadProcessId
0x180051602  test    eax, eax
0x180051604  jz      loc_18005149E
0x18005160a  mov     r8d, [rsp+498h+dwProcessId]; dwProcessId
0x18005160f  xor     edx, edx; bInheritHandle
0x180051611  mov     ecx, 1000h; dwDesiredAccess
0x180051616  call    cs:__imp_OpenProcess
0x18005161c  mov     rdi, rax
0x18005161f  mov     qword ptr [rsp+498h+var_460], rax
0x180051624  dec     rax
0x180051627  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005162b  jbe     loc_180051706
0x180051631  lea     rax, [rdi-1]
0x180051635  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180051639  ja      loc_18005149E
0x18005163f  mov     rcx, rdi; hObject
0x180051642  call    cs:__imp_CloseHandle
0x180051648  jmp     loc_18005149E
0x18005164d  mov     r13d, 80070490h
0x180051653  jmp     loc_18005151C
0x180051658  mov     rax, rsi
0x18005165b  jmp     loc_1800514EB
0x180051660  mov     r8d, 100h; nSize
0x180051666  lea     rdx, [rsp+498h+Buffer]; lpBuffer
0x18005166e  movzx   ecx, ax; nAtom
0x180051671  call    cs:__imp_GlobalGetAtomNameW
0x180051677  test    eax, eax
0x180051679  jz      loc_1800515E4
0x18005167f  mov     r12d, eax
0x180051682  lea     rbx, [rsp+498h+Buffer]
0x18005168a  cmp     eax, 7FFFFFFFh
0x18005168f  mov     eax, r12d
0x180051692  jnb     short loc_1800516FF
0x180051694  cmp     word ptr [rbx], 0
0x180051698  jz      short loc_1800516A4
0x18005169a  add     rbx, 2
0x18005169e  sub     rax, 1
0x1800516a2  jnz     short loc_180051694
0x1800516a4  lea     r15, ds:2[r12*2]
0x1800516ac  mov     rcx, r15; cb
0x1800516af  call    cs:__imp_CoTaskMemAlloc
0x1800516b5  mov     rbp, rax
0x1800516b8  test    rax, rax
0x1800516bb  jz      loc_18005188B
0x1800516c1  lea     rax, [rsp+498h+Buffer]
0x1800516c9  sub     rbx, rax
0x1800516cc  sar     rbx, 1
0x1800516cf  add     rbx, rbx
0x1800516d2  mov     r9, rbx; SourceSize
0x1800516d5  lea     r8, [rsp+498h+Buffer]; Source
0x1800516dd  mov     rdx, r15; DestinationSize
0x1800516e0  mov     rcx, rbp; Destination
0x1800516e3  call    memcpy_s
0x1800516e8  xor     eax, eax
0x1800516ea  mov     [rbx+rbp], ax
0x1800516ee  mov     [rbp+r12*2+0], ax
0x1800516f4  mov     [r14], rbp
0x1800516f7  xor     r12d, r12d
0x1800516fa  jmp     loc_1800515E4
0x1800516ff  mov     eax, 7FFFFFFFh
0x180051704  jmp     short loc_180051694
0x180051706  mov     rcx, [r14]; pv
0x180051709  test    rcx, rcx
0x18005170c  jz      short loc_180051714
0x18005170e  call    cs:__imp_CoTaskMemFree
0x180051714  mov     [r14+8], rsi
0x180051718  mov     [r14+10h], rsi
0x18005171c  mov     [r14], r12
0x18005171f  mov     r8d, [rsp+498h+dwProcessId]; dwProcessId
0x180051724  xor     edx, edx; bInheritHandle
0x180051726  mov     ecx, 1000h; dwDesiredAccess
0x18005172b  call    cs:__imp_OpenProcess
0x180051731  mov     rbx, rax
0x180051734  test    rax, rax
0x180051737  jz      loc_1800518CB
0x18005173d  mov     rdx, r14; void *
0x180051740  mov     rcx, rax; ProcessHandle
0x180051743  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x180051748  mov     ebp, eax
0x18005174a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18005174e  jz      short loc_180051759
0x180051750  mov     rcx, rbx; hObject
0x180051753  call    cs:__imp_CloseHandle
0x180051759  test    ebp, ebp
0x18005175b  jns     loc_180051631
0x180051761  mov     rcx, [r14]; pv
0x180051764  test    rcx, rcx
0x180051767  jz      short loc_18005176F
0x180051769  call    cs:__imp_CoTaskMemFree
0x18005176f  mov     [r14+8], rsi
0x180051773  mov     [r14+10h], rsi
0x180051777  mov     [r14], r12
0x18005177a  xor     edx, edx; Val
0x18005177c  mov     r8d, 200h; Size
0x180051782  lea     rcx, [rsp+498h+ProcessInformation]; void *
0x180051787  call    memset_0
0x18005178c  mov     [rsp+498h+var_460], r12d
0x180051791  lea     rax, [rsp+498h+var_460]
0x180051796  mov     qword ptr [rsp+498h+ReturnLength], rax; int
0x18005179b  mov     r9d, 200h; ProcessInformationLength
0x1800517a1  lea     r8, [rsp+498h+ProcessInformation]; ProcessInformation
0x1800517a6  mov     edx, 32h ; '2'; ProcessInformationClass
0x1800517ab  mov     rcx, rdi; ProcessHandle
0x1800517ae  call    cs:__imp_NtQueryInformationProcess
0x1800517b4  test    eax, eax
0x1800517b6  js      loc_180051849
0x1800517bc  test    [rsp+498h+ProcessInformation], 1000h
0x1800517c4  jz      loc_180051631
0x1800517ca  movzx   ecx, [rsp+498h+var_444]
0x1800517cf  shr     rcx, 1
0x1800517d2  mov     rax, rcx
0x1800517d5  lea     rbx, [rsp+498h+Src]
0x1800517da  jz      short loc_1800517F0
0x1800517dc  nop     dword ptr [rax+00h]
0x1800517e0  cmp     word ptr [rbx], 0
0x1800517e4  jz      short loc_1800517F0
0x1800517e6  add     rbx, 2
0x1800517ea  sub     rax, 1
0x1800517ee  jnz     short loc_1800517E0
0x1800517f0  lea     r12, [rcx+rcx]
0x1800517f4  lea     r15, [r12+2]
0x1800517f9  mov     rcx, r15; cb
0x1800517fc  call    cs:__imp_CoTaskMemAlloc
0x180051802  mov     rbp, rax
0x180051805  test    rax, rax
0x180051808  jz      short loc_18005186A
0x18005180a  lea     rax, [rsp+498h+Src]
0x18005180f  sub     rbx, rax
0x180051812  sar     rbx, 1
0x180051815  add     rbx, rbx
0x180051818  jz      short loc_180051833
0x18005181a  mov     rcx, rbp; void *
0x18005181d  cmp     r15, rbx
0x180051820  jb      loc_1800518EC
0x180051826  mov     r8, rbx; Size
0x180051829  lea     rdx, [rsp+498h+Src]; Src
0x18005182e  call    memcpy_0
0x180051833  xor     eax, eax
0x180051835  mov     [rbx+rbp], ax
0x180051839  mov     [r12+rbp], ax
0x18005183e  mov     [r14], rbp
0x180051841  xor     r12d, r12d
0x180051844  jmp     loc_180051631
0x180051849  mov     rcx, [rsp+498h]; this
0x180051851  mov     r9d, eax; char *
0x180051854  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18005185b  mov     edx, 191h; void *
0x180051860  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180051865  jmp     loc_180051631
0x18005186a  mov     [r14], rbp
0x18005186d  mov     rcx, [rsp+498h]; this
0x180051875  mov     r9d, r13d; char *
0x180051878  lea     r8, aOnecoreShellLi_2; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18005187f  mov     edx, 196h; void *
0x180051884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051889  jmp     short loc_180051841
0x18005188b  mov     [r14], rbp
0x18005188e  mov     rcx, [rsp+498h]; this
0x180051896  mov     r9d, r13d; char *
0x180051899  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800518a0  mov     edx, 60h ; '`'; void *
0x1800518a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800518aa  mov     rcx, [rsp+498h]; this
0x1800518b2  mov     r9d, r13d; char *
0x1800518b5  lea     r8, aPcshellTwinuiA_43; "pcshell\\twinui\\appmanager\\lib\\class"...
0x1800518bc  mov     edx, 158h; void *
0x1800518c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800518c6  jmp     loc_18005151C
0x1800518cb  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800518d0  mov     ebp, eax
0x1800518d2  test    eax, eax
0x1800518d4  js      loc_180051759
0x1800518da  mov     rdx, r14; void *
0x1800518dd  mov     rcx, rbx; ProcessHandle
0x1800518e0  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800518e5  mov     ebp, eax
0x1800518e7  jmp     loc_180051759
0x1800518ec  mov     r8, r15; Size
0x1800518ef  xor     edx, edx; Val
0x1800518f1  call    memset_0
0x1800518f6  call    cs:__imp__o__errno
0x1800518fc  mov     dword ptr [rax], 22h ; '"'
0x180051902  call    _invalid_parameter_noinfo
0x180051907  jmp     loc_180051833
0x18005190c  mov     [rax], r12w
0x180051910  mov     r13d, r12d
0x180051913  jmp     loc_180051519
0x180051918  mov     [rax], r12w
  ... truncated ...
```
