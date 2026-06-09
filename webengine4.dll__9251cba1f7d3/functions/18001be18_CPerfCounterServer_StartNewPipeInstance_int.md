# CPerfCounterServer::StartNewPipeInstance(int)

- ea: `0x18001be18`
- end: `0x18001c04d`
- name: `?StartNewPipeInstance@CPerfCounterServer@@AEAAJH@Z`
- size: `565`
- prototype: `__int64 __fastcall(CPerfCounterServer *__hidden this, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001b4d0`
- `0x18001b910`
- `0x18001bc8c`

## callees

- `0x18001b018`
- `0x18001b228`
- `0x18001be18`
- `0x18001d3c0`
- `0x18004d690`
- `0x18004d754`

## import_xrefs

- `KERNEL32!CreateNamedPipeW` at `0x18001bf94`
- `KERNEL32!CreateNamedPipeW` at `0x18001bff5`
- `KERNEL32!CreateNamedPipeW` at `0x18001bf94`
- `KERNEL32!CreateNamedPipeW` at `0x18001bff5`
- `ADVAPI32!RegCloseKey` at `0x18001c024`
- `ADVAPI32!RegCloseKey` at `0x18001c024`
- `ADVAPI32!RegOpenKeyExW` at `0x18001bf22`
- `ADVAPI32!RegOpenKeyExW` at `0x18001bf22`

## string_xrefs

- `0x18001bf14`: `SYSTEM\CurrentControlSet\Services\ASP.NET_4.0.30319\Names`

## pseudocode

```c
__int64 __fastcall CPerfCounterServer::StartNewPipeInstance(CPerfCounterServer *this, int a2)
{
  bool v3; // cc
  void *v5; // rsi
  unsigned int RandomString; // ebx
  unsigned int Sd; // eax
  _WORD *v8; // rax
  _WORD *v9; // rcx
  __int64 v10; // rdx
  char *v11; // r8
  __int16 v12; // ax
  _WORD *v13; // rax
  __int64 v14; // r14
  LSTATUS v15; // eax
  int i; // r15d
  HANDLE v17; // rax
  int j; // r14d
  HANDLE v19; // rax
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+90h] [rbp+30h] BYREF
  void *v23; // [rsp+A0h] [rbp+40h] BYREF

  v3 = *((_DWORD *)this + 13) < 32;
  hKey = 0;
  v5 = 0;
  v23 = 0;
  if ( v3 )
  {
    Sd = CPerfCounterServer::CreateSd(this, (struct _ACL **)&v23);
    v5 = v23;
    RandomString = Sd;
    if ( !Sd )
    {
      SecurityAttributes.nLength = 24;
      SecurityAttributes.lpSecurityDescriptor = v23;
      SecurityAttributes.bInheritHandle = 0;
      if ( a2 )
      {
        v8 = MemAlloc(0x100u);
        *((_QWORD *)this + 7) = v8;
        v9 = v8;
        if ( v8 )
        {
          v10 = 10;
          v11 = (char *)((char *)L"\\\\.\\pipe\\" - (char *)v8);
          do
          {
            if ( v10 == -2147483636 )
              break;
            v12 = *(_WORD *)((char *)v9 + (_QWORD)v11);
            if ( !v12 )
              break;
            *v9++ = v12;
            --v10;
          }
          while ( v10 );
          v13 = v9 - 1;
          if ( v10 )
            v13 = v9;
          *v13 = 0;
          RandomString = v10 == 0 ? 0x8007007A : 0;
          if ( v10 )
          {
            v14 = *((_QWORD *)this + 7);
            v15 = RegOpenKeyExW(
                    HKEY_LOCAL_MACHINE,
                    L"SYSTEM\\CurrentControlSet\\Services\\ASP.NET_4.0.30319\\Names",
                    0,
                    0x2001Fu,
                    &hKey);
            if ( v15 )
            {
              RandomString = (unsigned __int16)v15 | 0x80070000;
              if ( v15 <= 0 )
                RandomString = v15;
            }
            else
            {
              for ( i = 0; i < 5; ++i )
              {
                RandomString = GenerateRandomString((unsigned __int16 *)(v14 + 18), 119);
                if ( RandomString )
                  break;
                *(_WORD *)(v14 + 254) = 0;
                v17 = CreateNamedPipeW(
                        *((LPCWSTR *)this + 7),
                        0x40080003u,
                        6u,
                        0x20u,
                        0x400u,
                        0x400u,
                        0x3E8u,
                        &SecurityAttributes);
                RandomString = CPerfCounterServer::EnsureConnection(this, v17, (LPCWSTR)(v14 + 18), hKey);
                if ( !RandomString )
                  break;
              }
            }
          }
        }
        else
        {
          RandomString = -2147024882;
        }
      }
      else
      {
        for ( j = 0; j < 5; ++j )
        {
          v19 = CreateNamedPipeW(
                  *((LPCWSTR *)this + 7),
                  0x40000003u,
                  6u,
                  0x20u,
                  0x400u,
                  0x400u,
                  0x3E8u,
                  &SecurityAttributes);
          RandomString = CPerfCounterServer::EnsureConnection(this, v19, 0, 0);
          if ( !RandomString )
            break;
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    RandomString = -2147418113;
  }
  MemFree(v5);
  return RandomString;
}

```

## disassembly

```asm
0x18001be18  mov     [rsp-28h+arg_8], rbx
0x18001be1d  mov     [rsp-28h+arg_18], rsi
0x18001be22  push    rbp
0x18001be23  push    rdi
0x18001be24  push    r13
0x18001be26  push    r14
0x18001be28  push    r15
0x18001be2a  mov     rbp, rsp
0x18001be2d  sub     rsp, 60h
0x18001be31  xor     r13d, r13d
0x18001be34  mov     r14d, edx
0x18001be37  cmp     dword ptr [rcx+34h], 20h ; ' '
0x18001be3b  mov     rdi, rcx
0x18001be3e  mov     [rbp+hKey], r13
0x18001be42  mov     esi, r13d
0x18001be45  mov     [rbp+arg_10], r13
0x18001be49  jl      short loc_18001BE55
0x18001be4b  mov     ebx, 8000FFFFh
0x18001be50  jmp     loc_18001C02A
0x18001be55  lea     rdx, [rbp+arg_10]; void **
0x18001be59  call    ?CreateSd@CPerfCounterServer@@AEAAJPEAPEAX@Z; CPerfCounterServer::CreateSd(void * *)
0x18001be5e  mov     rsi, [rbp+arg_10]
0x18001be62  mov     ebx, eax
0x18001be64  test    eax, eax
0x18001be66  jnz     loc_18001C01B
0x18001be6c  mov     [rbp+SecurityAttributes.nLength], 18h
0x18001be73  mov     [rbp+SecurityAttributes.lpSecurityDescriptor], rsi
0x18001be77  mov     [rbp+SecurityAttributes.bInheritHandle], r13d
0x18001be7b  test    r14d, r14d
0x18001be7e  jz      loc_18001BFBE
0x18001be84  mov     ecx, 100h; unsigned __int64
0x18001be89  call    ?MemAlloc@@YAPEAX_K@Z; MemAlloc(unsigned __int64)
0x18001be8e  mov     [rdi+38h], rax
0x18001be92  mov     rcx, rax
0x18001be95  test    rax, rax
0x18001be98  jnz     short loc_18001BEA4
0x18001be9a  mov     ebx, 8007000Eh
0x18001be9f  jmp     loc_18001C01B
0x18001bea4  lea     r8, aPipe; "\\\\.\\pipe\\"
0x18001beab  mov     edx, 0Ah
0x18001beb0  sub     r8, rax
0x18001beb3  lea     rax, [rdx+7FFFFFF4h]
0x18001beba  test    rax, rax
0x18001bebd  jz      short loc_18001BED6
0x18001bebf  movzx   eax, word ptr [r8+rcx]
0x18001bec4  test    ax, ax
0x18001bec7  jz      short loc_18001BED6
0x18001bec9  mov     [rcx], ax
0x18001becc  add     rcx, 2
0x18001bed0  sub     rdx, 1
0x18001bed4  jnz     short loc_18001BEB3
0x18001bed6  test    rdx, rdx
0x18001bed9  lea     rax, [rcx-2]
0x18001bedd  cmovnz  rax, rcx
0x18001bee1  mov     [rax], r13w
0x18001bee5  mov     rax, rdx
0x18001bee8  neg     rax
0x18001beeb  sbb     ebx, ebx
0x18001beed  not     ebx
0x18001beef  and     ebx, 8007007Ah
0x18001bef5  test    rdx, rdx
0x18001bef8  jz      loc_18001C01B
0x18001befe  mov     r14, [rdi+38h]
0x18001bf02  lea     rax, [rbp+hKey]
0x18001bf06  mov     r9d, 2001Fh; samDesired
0x18001bf0c  mov     [rsp+60h+phkResult], rax; phkResult
0x18001bf11  xor     r8d, r8d; ulOptions
0x18001bf14  lea     rdx, aSystemCurrentc_8; "SYSTEM\\CurrentControlSet\\Services\\AS"...
0x18001bf1b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bf22  call    cs:__imp_RegOpenKeyExW
0x18001bf28  test    eax, eax
0x18001bf2a  jz      short loc_18001BF3F
0x18001bf2c  movzx   ebx, ax
0x18001bf2f  or      ebx, 80070000h
0x18001bf35  test    eax, eax
0x18001bf37  cmovle  ebx, eax
0x18001bf3a  jmp     loc_18001C01B
0x18001bf3f  mov     r15d, r13d
0x18001bf42  mov     edx, 77h ; 'w'; int
0x18001bf47  lea     rcx, [r14+12h]; unsigned __int16 *
0x18001bf4b  call    ?GenerateRandomString@@YAJPEAGH@Z; GenerateRandomString(ushort *,int)
0x18001bf50  mov     ebx, eax
0x18001bf52  test    eax, eax
0x18001bf54  jnz     loc_18001C01B
0x18001bf5a  lea     rax, [rbp+SecurityAttributes]
0x18001bf5e  mov     [r14+0FEh], r13w
0x18001bf66  mov     rcx, [rdi+38h]; lpName
0x18001bf6a  lea     r9d, [rbx+20h]; nMaxInstances
0x18001bf6e  mov     [rsp+60h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001bf73  lea     r8d, [rbx+6]; dwPipeMode
0x18001bf77  mov     [rsp+60h+nDefaultTimeOut], 3E8h; nDefaultTimeOut
0x18001bf7f  mov     edx, 40080003h; dwOpenMode
0x18001bf84  mov     [rsp+60h+nInBufferSize], 400h; nInBufferSize
0x18001bf8c  mov     dword ptr [rsp+60h+phkResult], 400h; nOutBufferSize
0x18001bf94  call    cs:__imp_CreateNamedPipeW
0x18001bf9a  mov     r9, [rbp+hKey]; hKey
0x18001bf9e  lea     r8, [r14+12h]; lpValueName
0x18001bfa2  mov     rdx, rax; hNamedPipe
0x18001bfa5  mov     rcx, rdi; this
0x18001bfa8  call    ?EnsureConnection@CPerfCounterServer@@AEAAJPEAXPEAGPEAUHKEY__@@@Z; CPerfCounterServer::EnsureConnection(void *,ushort *,HKEY__ *)
0x18001bfad  mov     ebx, eax
0x18001bfaf  test    eax, eax
0x18001bfb1  jz      short loc_18001C01B
0x18001bfb3  inc     r15d
0x18001bfb6  cmp     r15d, 5
0x18001bfba  jl      short loc_18001BF42
0x18001bfbc  jmp     short loc_18001C01B
0x18001bfbe  mov     r14d, r13d
0x18001bfc1  mov     rcx, [rdi+38h]; lpName
0x18001bfc5  lea     rax, [rbp+SecurityAttributes]
0x18001bfc9  mov     [rsp+60h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18001bfce  mov     r9d, 20h ; ' '; nMaxInstances
0x18001bfd4  mov     [rsp+60h+nDefaultTimeOut], 3E8h; nDefaultTimeOut
0x18001bfdc  mov     edx, 40000003h; dwOpenMode
0x18001bfe1  mov     [rsp+60h+nInBufferSize], 400h; nInBufferSize
0x18001bfe9  mov     dword ptr [rsp+60h+phkResult], 400h; nOutBufferSize
0x18001bff1  lea     r8d, [r9-1Ah]; dwPipeMode
0x18001bff5  call    cs:__imp_CreateNamedPipeW
0x18001bffb  xor     r9d, r9d; hKey
0x18001bffe  xor     r8d, r8d; lpValueName
0x18001c001  mov     rdx, rax; hNamedPipe
0x18001c004  mov     rcx, rdi; this
0x18001c007  call    ?EnsureConnection@CPerfCounterServer@@AEAAJPEAXPEAGPEAUHKEY__@@@Z; CPerfCounterServer::EnsureConnection(void *,ushort *,HKEY__ *)
0x18001c00c  mov     ebx, eax
0x18001c00e  test    eax, eax
0x18001c010  jz      short loc_18001C01B
0x18001c012  inc     r14d
0x18001c015  cmp     r14d, 5
0x18001c019  jl      short loc_18001BFC1
0x18001c01b  mov     rcx, [rbp+hKey]; hKey
0x18001c01f  test    rcx, rcx
0x18001c022  jz      short loc_18001C02A
0x18001c024  call    cs:__imp_RegCloseKey
0x18001c02a  mov     rcx, rsi; lpMem
0x18001c02d  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x18001c032  lea     r11, [rsp+60h+var_s0]
0x18001c037  mov     eax, ebx
0x18001c039  mov     rbx, [r11+38h]
0x18001c03d  mov     rsi, [r11+48h]
0x18001c041  mov     rsp, r11
0x18001c044  pop     r15
0x18001c046  pop     r14
0x18001c048  pop     r13
0x18001c04a  pop     rdi
0x18001c04b  pop     rbp
0x18001c04c  retn
```
