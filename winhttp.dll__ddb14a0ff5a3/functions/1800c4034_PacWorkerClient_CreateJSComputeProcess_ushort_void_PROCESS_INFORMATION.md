# PacWorkerClient::CreateJSComputeProcess(ushort *,void *,_PROCESS_INFORMATION *)

- ea: `0x1800c4034`
- end: `0x1800c44a5`
- name: `?CreateJSComputeProcess@PacWorkerClient@@AEAAJPEAGPEAXPEAU_PROCESS_INFORMATION@@@Z`
- size: `1137`
- prototype: `__int64 __fastcall(PacWorkerClient *__hidden this, unsigned __int16 *, void *, LPPROCESS_INFORMATION lpProcessInformation)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c44ac`

## callees

- `0x1800081a0`
- `0x18001b480`
- `0x180091764`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c4034`
- `0x1800c5830`
- `0x1800da434`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800c40ee`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800c413d`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800c40ee`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800c413d`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c419f`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c4213`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c4281`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c42dd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c433c`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c419f`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c4213`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c4281`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c42dd`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800c433c`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800c43f2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800c43f2`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800c4434`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800c4434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c41a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c421d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c428b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c42e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c43fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c41a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c421d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c428b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c42e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c43fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c447d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c447d`

## pseudocode

```c
__int64 __fastcall PacWorkerClient::CreateJSComputeProcess(
        PacWorkerClient *this,
        unsigned __int16 *a2,
        void *a3,
        LPPROCESS_INFORMATION lpProcessInformation)
{
  struct _SECURITY_DESCRIPTOR *v4; // rdi
  int v7; // r14d
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  HANDLE v12; // rbx
  int v13; // r13d
  __int64 v14; // rcx
  LPPROCESS_INFORMATION v15; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v16; // r14
  __int64 v17; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST *Heap; // rax
  signed int v19; // esi
  signed int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax
  signed int v24; // eax
  RestrictedToken *v25; // rcx
  signed int v26; // eax
  int RestrictedTokenAndSecurityDescriptor; // eax
  signed int LastError; // eax
  SIZE_T cbSize; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_DESCRIPTOR *v31; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hToken; // [rsp+70h] [rbp-90h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v33; // [rsp+78h] [rbp-88h] BYREF
  __int128 v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+90h] [rbp-70h]
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+B0h] [rbp-50h] BYREF
  struct _PROC_THREAD_ATTRIBUTE_LIST *v38; // [rsp+118h] [rbp+18h]
  int Value; // [rsp+120h] [rbp+20h] BYREF
  ULONG_PTR Size; // [rsp+128h] [rbp+28h] BYREF
  __int128 v41; // [rsp+130h] [rbp+30h] BYREF

  v4 = 0;
  v7 = (int)this;
  memset_0(&StartupInfo, 0, 0x70u);
  Size = 0;
  Value = 0;
  v35 = 0;
  v12 = 0;
  v41 = 0;
  v13 = 0;
  hToken = 0;
  v34 = 0;
  v31 = 0;
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qS_sid_(v10, v9, v11, v7, (__int64)a2, a3);
  if ( lpProcessInformation )
  {
    v14 = 24;
    v15 = lpProcessInformation;
    do
    {
      LOBYTE(v15->hProcess) = 0;
      v15 = (LPPROCESS_INFORMATION)((char *)v15 + 1);
      --v14;
    }
    while ( v14 );
  }
  InitializeProcThreadAttributeList(0, 5u, 0, &Size);
  v16 = 0;
  v33 = 0;
  Heap = (struct _PROC_THREAD_ATTRIBUTE_LIST *)WxAllocateHeapEx(v17, (unsigned int)Size);
  if ( Heap )
  {
    v16 = Heap;
    v33 = Heap;
    if ( InitializeProcThreadAttributeList(Heap, 5u, 0, &Size) )
    {
      v13 = 1;
      Value = 1;
      if ( UpdateProcThreadAttribute(v16, 0, 0x2000Eu, &Value, 4u, 0, 0) )
      {
        *(_QWORD *)&v41 = 0x1111131111111305LL;
        *((_QWORD *)&v41 + 1) = 0x101000130211110LL;
        if ( UpdateProcThreadAttribute(v16, 0, 0x20007u, &v41, 0x10u, 0, 0) )
        {
          *((_QWORD *)&v34 + 1) = &off_1800E3040;
          LODWORD(v35) = 4;
          *(_QWORD *)&v34 = a3;
          if ( UpdateProcThreadAttribute(v16, 0, 0x20009u, &v34, 0x18u, 0, 0) )
          {
            Value = 1;
            if ( UpdateProcThreadAttribute(v16, 0, 0x2000Fu, &Value, 4u, 0, 0) )
            {
              Value = -1;
              if ( UpdateProcThreadAttribute(v16, 0, 0x2000Bu, &Value, 4u, 0, 0) )
              {
                StartupInfo.cb = 112;
                v38 = v16;
                RestrictedTokenAndSecurityDescriptor = RestrictedToken::GetRestrictedTokenAndSecurityDescriptor(
                                                         v25,
                                                         a3,
                                                         &hToken,
                                                         &v31);
                v4 = v31;
                v19 = RestrictedTokenAndSecurityDescriptor;
                if ( RestrictedTokenAndSecurityDescriptor >= 0 )
                {
                  ProcessAttributes.bInheritHandle = 0;
                  v12 = hToken;
                  ProcessAttributes.nLength = 24;
                  ProcessAttributes.lpSecurityDescriptor = v31;
                  if ( CreateProcessAsUserW(
                         hToken,
                         0,
                         a2,
                         &ProcessAttributes,
                         0,
                         1,
                         0xC0000u,
                         0,
                         0,
                         &StartupInfo,
                         lpProcessInformation) )
                  {
                    v19 = 0;
                  }
                  else
                  {
                    LastError = GetLastError();
                    v19 = LastError;
                    if ( LastError > 0 )
                      v19 = (unsigned __int16)LastError | 0x80070000;
                    if ( v19 >= 0 )
                      v19 = -2147418113;
                  }
                }
                else
                {
                  v12 = hToken;
                }
              }
              else
              {
                v26 = GetLastError();
                v19 = v26;
                if ( v26 > 0 )
                  v19 = (unsigned __int16)v26 | 0x80070000;
                if ( v19 >= 0 )
                  v19 = -2147418113;
              }
            }
            else
            {
              v24 = GetLastError();
              v19 = v24;
              if ( v24 > 0 )
                v19 = (unsigned __int16)v24 | 0x80070000;
              if ( v19 >= 0 )
                v19 = -2147418113;
            }
          }
          else
          {
            v23 = GetLastError();
            v19 = v23;
            if ( v23 > 0 )
              v19 = (unsigned __int16)v23 | 0x80070000;
            if ( v19 >= 0 )
              v19 = -2147418113;
          }
        }
        else
        {
          v22 = GetLastError();
          v19 = v22;
          if ( v22 > 0 )
            v19 = (unsigned __int16)v22 | 0x80070000;
          if ( v19 >= 0 )
            v19 = -2147418113;
        }
      }
      else
      {
        v21 = GetLastError();
        v19 = v21;
        if ( v21 > 0 )
          v19 = (unsigned __int16)v21 | 0x80070000;
        if ( v19 >= 0 )
          v19 = -2147418113;
      }
    }
    else
    {
      v20 = GetLastError();
      v19 = v20;
      if ( v20 > 0 )
        v19 = (unsigned __int16)v20 | 0x80070000;
      if ( v19 >= 0 )
        v19 = -2147418113;
    }
  }
  else
  {
    v19 = -2147024882;
  }
  if ( v16 )
  {
    if ( v13 )
      DeleteProcThreadAttributeList(v16);
    WxFreeHeapEx(&v33);
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 23, WPP_7537b208fef33d19ae8f417444b45cbe_Traceguids, (unsigned int)v19, cbSize);
  if ( v4 )
    WxLocalAllocator::Free((void **)&v31);
  if ( v12 )
    CloseHandle(v12);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800c4034  push    rbp
0x1800c4036  push    rbx
0x1800c4037  push    rsi
0x1800c4038  push    rdi
0x1800c4039  push    r12
0x1800c403b  push    r13
0x1800c403d  push    r14
0x1800c403f  push    r15
0x1800c4041  lea     rbp, [rsp-58h]
0x1800c4046  sub     rsp, 158h
0x1800c404d  mov     rax, cs:__security_cookie
0x1800c4054  xor     rax, rsp
0x1800c4057  mov     [rbp+90h+var_50], rax
0x1800c405b  xor     edi, edi
0x1800c405d  mov     rsi, r8
0x1800c4060  mov     r12, rdx
0x1800c4063  mov     [rsp+190h+var_12C], edi
0x1800c4067  mov     r14, rcx
0x1800c406a  xor     edx, edx; Val
0x1800c406c  lea     rcx, [rbp+90h+StartupInfo]; void *
0x1800c4070  mov     r15, r9
0x1800c4073  lea     r8d, [rdi+70h]; Size
0x1800c4077  call    memset_0
0x1800c407c  xorps   xmm0, xmm0
0x1800c407f  mov     [rbp+90h+Size], rdi
0x1800c4083  xor     eax, eax
0x1800c4085  mov     [rbp+90h+Value], edi
0x1800c4088  xorps   xmm1, xmm1
0x1800c408b  mov     [rbp+90h+var_100], rax
0x1800c408f  mov     ebx, edi
0x1800c4091  mov     qword ptr [rbp+90h+ProcessAttributes.bInheritHandle], rax
0x1800c4095  movups  [rbp+90h+var_60], xmm0
0x1800c4099  mov     r13d, edi
0x1800c409c  mov     [rsp+190h+hToken], rbx
0x1800c40a1  movups  [rbp+90h+var_110], xmm1
0x1800c40a5  mov     [rsp+190h+var_128], rdi
0x1800c40aa  movups  xmmword ptr [rbp+90h+ProcessAttributes.nLength], xmm0
0x1800c40ae  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c40b5  jz      short loc_1800C40C9
0x1800c40b7  mov     [rsp+190h+lpPreviousValue], rsi; pSid
0x1800c40bc  mov     r9, r14; int
0x1800c40bf  mov     [rsp+190h+cbSize], r12; __int64
0x1800c40c4  call    WPP_SF_qS_sid_
0x1800c40c9  test    r15, r15
0x1800c40cc  jz      short loc_1800C40E1
0x1800c40ce  mov     ecx, 18h
0x1800c40d3  mov     rax, r15
0x1800c40d6  mov     [rax], bl
0x1800c40d8  inc     rax
0x1800c40db  sub     rcx, 1
0x1800c40df  jnz     short loc_1800C40D6
0x1800c40e1  xor     r8d, r8d; dwFlags
0x1800c40e4  lea     r9, [rbp+90h+Size]; lpSize
0x1800c40e8  xor     ecx, ecx; lpAttributeList
0x1800c40ea  lea     edx, [r8+5]; dwAttributeCount
0x1800c40ee  call    cs:__imp_InitializeProcThreadAttributeList
0x1800c40f4  mov     edx, dword ptr [rbp+90h+Size]
0x1800c40f7  xor     r14d, r14d
0x1800c40fa  mov     [rsp+190h+var_12C], ebx
0x1800c40fe  mov     [rsp+190h+var_118], r14
0x1800c4103  call    WxAllocateHeapEx
0x1800c4108  test    rax, rax
0x1800c410b  jnz     short loc_1800C4127
0x1800c410d  mov     [rsp+190h+var_12C], 34h ; '4'
0x1800c4115  mov     esi, 8007000Eh
0x1800c411a  mov     [rsp+190h+var_12C], 168h
0x1800c4122  jmp     loc_1800C4427
0x1800c4127  mov     r14, rax
0x1800c412a  mov     [rsp+190h+var_118], rax
0x1800c412f  xor     r8d, r8d; dwFlags
0x1800c4132  lea     r9, [rbp+90h+Size]; lpSize
0x1800c4136  mov     rcx, rax; lpAttributeList
0x1800c4139  lea     edx, [r8+5]; dwAttributeCount
0x1800c413d  call    cs:__imp_InitializeProcThreadAttributeList
0x1800c4143  test    eax, eax
0x1800c4145  jnz     short loc_1800C4173
0x1800c4147  call    cs:__imp_GetLastError
0x1800c414d  mov     esi, eax
0x1800c414f  test    eax, eax
0x1800c4151  jle     short loc_1800C415C
0x1800c4153  movzx   esi, ax
0x1800c4156  or      esi, 80070000h
0x1800c415c  test    esi, esi
0x1800c415e  mov     [rsp+190h+var_12C], 16Dh
0x1800c4166  mov     eax, 8000FFFFh
0x1800c416b  cmovns  esi, eax
0x1800c416e  jmp     loc_1800C4427
0x1800c4173  mov     [rsp+190h+lpReturnSize], rbx; lpReturnSize
0x1800c4178  lea     r9, [rbp+90h+Value]; lpValue
0x1800c417c  mov     r13d, 1
0x1800c4182  mov     [rsp+190h+lpPreviousValue], rbx; lpPreviousValue
0x1800c4187  xor     edx, edx; dwFlags
0x1800c4189  mov     [rbp+90h+Value], r13d
0x1800c418d  mov     r8d, 2000Eh; Attribute
0x1800c4193  mov     [rsp+190h+cbSize], 4; cbSize
0x1800c419c  mov     rcx, r14; lpAttributeList
0x1800c419f  call    cs:__imp_UpdateProcThreadAttribute
0x1800c41a5  test    eax, eax
0x1800c41a7  jnz     short loc_1800C41D5
0x1800c41a9  call    cs:__imp_GetLastError
0x1800c41af  mov     esi, eax
0x1800c41b1  test    eax, eax
0x1800c41b3  jle     short loc_1800C41BE
0x1800c41b5  movzx   esi, ax
0x1800c41b8  or      esi, 80070000h
0x1800c41be  test    esi, esi
0x1800c41c0  mov     [rsp+190h+var_12C], 17Dh
0x1800c41c8  mov     eax, 8000FFFFh
0x1800c41cd  cmovns  esi, eax
0x1800c41d0  jmp     loc_1800C4427
0x1800c41d5  mov     rax, 1111131111111305h
0x1800c41df  mov     [rsp+190h+lpReturnSize], rbx; lpReturnSize
0x1800c41e4  mov     qword ptr [rbp+90h+var_60], rax
0x1800c41e8  lea     r9, [rbp+90h+var_60]; lpValue
0x1800c41ec  mov     rax, 101000130211110h
0x1800c41f6  mov     [rsp+190h+lpPreviousValue], rbx; lpPreviousValue
0x1800c41fb  xor     edx, edx; dwFlags
0x1800c41fd  mov     qword ptr [rbp+90h+var_60+8], rax
0x1800c4201  mov     r8d, 20007h; Attribute
0x1800c4207  mov     [rsp+190h+cbSize], 10h; cbSize
0x1800c4210  mov     rcx, r14; lpAttributeList
0x1800c4213  call    cs:__imp_UpdateProcThreadAttribute
0x1800c4219  test    eax, eax
0x1800c421b  jnz     short loc_1800C4249
0x1800c421d  call    cs:__imp_GetLastError
0x1800c4223  mov     esi, eax
0x1800c4225  test    eax, eax
0x1800c4227  jle     short loc_1800C4232
0x1800c4229  movzx   esi, ax
0x1800c422c  or      esi, 80070000h
0x1800c4232  test    esi, esi
0x1800c4234  mov     [rsp+190h+var_12C], 1A6h
0x1800c423c  mov     eax, 8000FFFFh
0x1800c4241  cmovns  esi, eax
0x1800c4244  jmp     loc_1800C4427
0x1800c4249  lea     rax, off_1800E3040
0x1800c4250  mov     [rsp+190h+lpReturnSize], rbx; lpReturnSize
0x1800c4255  mov     [rsp+190h+lpPreviousValue], rbx; lpPreviousValue
0x1800c425a  lea     r9, [rbp+90h+var_110]; lpValue
0x1800c425e  xor     edx, edx; dwFlags
0x1800c4260  mov     qword ptr [rbp+90h+var_110+8], rax
0x1800c4264  mov     r8d, 20009h; Attribute
0x1800c426a  mov     [rsp+190h+cbSize], 18h; cbSize
0x1800c4273  mov     rcx, r14; lpAttributeList
0x1800c4276  mov     dword ptr [rbp+90h+var_100], 4
0x1800c427d  mov     qword ptr [rbp+90h+var_110], rsi
0x1800c4281  call    cs:__imp_UpdateProcThreadAttribute
0x1800c4287  test    eax, eax
0x1800c4289  jnz     short loc_1800C42B7
0x1800c428b  call    cs:__imp_GetLastError
0x1800c4291  mov     esi, eax
0x1800c4293  test    eax, eax
0x1800c4295  jle     short loc_1800C42A0
0x1800c4297  movzx   esi, ax
0x1800c429a  or      esi, 80070000h
0x1800c42a0  test    esi, esi
0x1800c42a2  mov     [rsp+190h+var_12C], 1B7h
0x1800c42aa  mov     eax, 8000FFFFh
0x1800c42af  cmovns  esi, eax
0x1800c42b2  jmp     loc_1800C4427
0x1800c42b7  mov     [rsp+190h+lpReturnSize], rbx; lpReturnSize
0x1800c42bc  lea     r9, [rbp+90h+Value]; lpValue
0x1800c42c0  mov     [rsp+190h+lpPreviousValue], rbx; lpPreviousValue
0x1800c42c5  xor     edx, edx; dwFlags
0x1800c42c7  mov     r8d, 2000Fh; Attribute
0x1800c42cd  mov     [rsp+190h+cbSize], 4; cbSize
0x1800c42d6  mov     rcx, r14; lpAttributeList
0x1800c42d9  mov     [rbp+90h+Value], r13d
0x1800c42dd  call    cs:__imp_UpdateProcThreadAttribute
0x1800c42e3  test    eax, eax
0x1800c42e5  jnz     short loc_1800C4313
0x1800c42e7  call    cs:__imp_GetLastError
0x1800c42ed  mov     esi, eax
0x1800c42ef  test    eax, eax
0x1800c42f1  jle     short loc_1800C42FC
0x1800c42f3  movzx   esi, ax
0x1800c42f6  or      esi, 80070000h
0x1800c42fc  test    esi, esi
0x1800c42fe  mov     [rsp+190h+var_12C], 1C5h
0x1800c4306  mov     eax, 8000FFFFh
0x1800c430b  cmovns  esi, eax
0x1800c430e  jmp     loc_1800C4427
0x1800c4313  mov     [rsp+190h+lpReturnSize], rbx; lpReturnSize
0x1800c4318  lea     r9, [rbp+90h+Value]; lpValue
0x1800c431c  mov     [rsp+190h+lpPreviousValue], rbx; lpPreviousValue
0x1800c4321  xor     edx, edx; dwFlags
0x1800c4323  mov     r8d, 2000Bh; Attribute
0x1800c4329  mov     [rsp+190h+cbSize], 4; cbSize
0x1800c4332  mov     rcx, r14; lpAttributeList
0x1800c4335  mov     [rbp+90h+Value], 0FFFFFFFFh
0x1800c433c  call    cs:__imp_UpdateProcThreadAttribute
0x1800c4342  test    eax, eax
0x1800c4344  jnz     short loc_1800C4372
0x1800c4346  call    cs:__imp_GetLastError
0x1800c434c  mov     esi, eax
0x1800c434e  test    eax, eax
0x1800c4350  jle     short loc_1800C435B
0x1800c4352  movzx   esi, ax
0x1800c4355  or      esi, 80070000h
0x1800c435b  test    esi, esi
0x1800c435d  mov     [rsp+190h+var_12C], 1D3h
0x1800c4365  mov     eax, 8000FFFFh
0x1800c436a  cmovns  esi, eax
0x1800c436d  jmp     loc_1800C4427
0x1800c4372  lea     r9, [rsp+190h+var_128]; struct _SECURITY_DESCRIPTOR **
0x1800c4377  mov     [rbp+90h+StartupInfo.cb], 70h ; 'p'
0x1800c437e  lea     r8, [rsp+190h+hToken]; void **
0x1800c4383  mov     [rbp+90h+var_78], r14
0x1800c4387  mov     rdx, rsi; void *
0x1800c438a  call    ?GetRestrictedTokenAndSecurityDescriptor@RestrictedToken@@QEAAJPEAXPEAPEAXPEAPEAU_SECURITY_DESCRIPTOR@@@Z; RestrictedToken::GetRestrictedTokenAndSecurityDescriptor(void *,void * *,_SECURITY_DESCRIPTOR * *)
0x1800c438f  mov     rdi, [rsp+190h+var_128]
0x1800c4394  mov     esi, eax
0x1800c4396  test    eax, eax
0x1800c4398  jns     short loc_1800C43A9
0x1800c439a  mov     rbx, [rsp+190h+hToken]
0x1800c439f  mov     [rsp+190h+var_12C], 1DFh
0x1800c43a7  jmp     short loc_1800C4427
0x1800c43a9  mov     [rsp+190h+lpProcessInformation], r15; lpProcessInformation
0x1800c43ae  lea     rax, [rbp+90h+StartupInfo]
0x1800c43b2  mov     [rsp+190h+lpStartupInfo], rax; lpStartupInfo
0x1800c43b7  lea     r9, [rbp+90h+ProcessAttributes]; lpProcessAttributes
0x1800c43bb  mov     [rsp+190h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x1800c43c0  mov     r8, r12; lpCommandLine
0x1800c43c3  mov     [rsp+190h+lpEnvironment], rbx; lpEnvironment
0x1800c43c8  xor     edx, edx; lpApplicationName
0x1800c43ca  mov     dword ptr [rsp+190h+lpReturnSize], 0C0000h; dwCreationFlags
0x1800c43d2  mov     [rbp+90h+ProcessAttributes.bInheritHandle], ebx
0x1800c43d5  mov     dword ptr [rsp+190h+lpPreviousValue], r13d; bInheritHandles
0x1800c43da  mov     [rsp+190h+cbSize], rbx; lpThreadAttributes
0x1800c43df  mov     rbx, [rsp+190h+hToken]
0x1800c43e4  mov     rcx, rbx; hToken
0x1800c43e7  mov     [rbp+90h+ProcessAttributes.nLength], 18h
0x1800c43ee  mov     [rbp+90h+ProcessAttributes.lpSecurityDescriptor], rdi
0x1800c43f2  call    cs:__imp_CreateProcessAsUserW
0x1800c43f8  test    eax, eax
0x1800c43fa  jnz     short loc_1800C4425
0x1800c43fc  call    cs:__imp_GetLastError
0x1800c4402  mov     esi, eax
0x1800c4404  test    eax, eax
0x1800c4406  jle     short loc_1800C4411
0x1800c4408  movzx   esi, ax
0x1800c440b  or      esi, 80070000h
0x1800c4411  test    esi, esi
0x1800c4413  mov     [rsp+190h+var_12C], 1EFh
0x1800c441b  mov     eax, 8000FFFFh
0x1800c4420  cmovns  esi, eax
0x1800c4423  jmp     short loc_1800C4427
0x1800c4425  xor     esi, esi
0x1800c4427  test    r14, r14
0x1800c442a  jz      short loc_1800C4444
0x1800c442c  test    r13d, r13d
0x1800c442f  jz      short loc_1800C443A
0x1800c4431  mov     rcx, r14; lpAttributeList
0x1800c4434  call    cs:__imp_DeleteProcThreadAttributeList
0x1800c443a  lea     rcx, [rsp+190h+var_118]
0x1800c443f  call    WxFreeHeapEx
0x1800c4444  test    byte ptr cs:xmmword_180107A60, 20h
0x1800c444b  jz      short loc_1800C4466
0x1800c444d  mov     edx, 17h
0x1800c4452  lea     r8, WPP_7537b208fef33d19ae8f417444b45cbe_Traceguids
0x1800c4459  mov     ecx, 405h
0x1800c445e  mov     r9d, esi
0x1800c4461  call    WPP_SF_d
0x1800c4466  test    rdi, rdi
0x1800c4469  jz      short loc_1800C4475
0x1800c446b  lea     rcx, [rsp+190h+var_128]; void **
0x1800c4470  call    ?Free@WxLocalAllocator@@SAXPEAPEAX@Z; WxLocalAllocator::Free(void * *)
0x1800c4475  test    rbx, rbx
0x1800c4478  jz      short loc_1800C4483
0x1800c447a  mov     rcx, rbx; hObject
0x1800c447d  call    cs:__imp_CloseHandle
0x1800c4483  mov     eax, esi
0x1800c4485  mov     rcx, [rbp+90h+var_50]
0x1800c4489  xor     rcx, rsp; StackCookie
0x1800c448c  call    __security_check_cookie
0x1800c4491  add     rsp, 158h
0x1800c4498  pop     r15
0x1800c449a  pop     r14
0x1800c449c  pop     r13
0x1800c449e  pop     r12
0x1800c44a0  pop     rdi
0x1800c44a1  pop     rsi
0x1800c44a2  pop     rbx
0x1800c44a3  pop     rbp
0x1800c44a4  retn
```
