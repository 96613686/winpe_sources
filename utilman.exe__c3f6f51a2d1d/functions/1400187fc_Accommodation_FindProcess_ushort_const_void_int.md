# Accommodation::FindProcess(ushort const *,void * *,int)

- ea: `0x1400187fc`
- end: `0x1400189d4`
- name: `?FindProcess@Accommodation@@SAKPEBGPEAPEAXH@Z`
- size: `472`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, void **, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400189dc`

## callees

- `0x140002480`
- `0x1400187fc`
- `0x1400269f0`

## import_xrefs

- `KERNEL32!K32GetModuleBaseNameW` at `0x14001895b`
- `KERNEL32!K32GetModuleBaseNameW` at `0x14001895b`
- `KERNEL32!K32EnumProcessModules` at `0x140018936`
- `KERNEL32!K32EnumProcessModules` at `0x140018936`
- `KERNEL32!K32EnumProcesses` at `0x140018856`
- `KERNEL32!K32EnumProcesses` at `0x140018856`
- `KERNEL32!OpenProcess` at `0x140018906`
- `KERNEL32!OpenProcess` at `0x140018906`
- `KERNEL32!CloseHandle` at `0x140018988`
- `KERNEL32!CloseHandle` at `0x140018988`
- `KERNEL32!GetCurrentProcessId` at `0x140018882`
- `KERNEL32!GetCurrentProcessId` at `0x140018882`
- `KERNEL32!ProcessIdToSessionId` at `0x1400188a0`
- `KERNEL32!ProcessIdToSessionId` at `0x1400188cf`
- `KERNEL32!ProcessIdToSessionId` at `0x1400188a0`
- `KERNEL32!ProcessIdToSessionId` at `0x1400188cf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018975`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140018975`

## pseudocode

```c
__int64 __fastcall Accommodation::FindProcess(const unsigned __int16 *a1, void **a2)
{
  DWORD CurrentProcessId; // eax
  DWORD v5; // r15d
  DWORD v6; // esi
  __int64 i; // rbx
  DWORD v8; // ecx
  DWORD v9; // r8d
  HANDLE v10; // rax
  void *v11; // rdi
  DWORD cbNeeded; // [rsp+20h] [rbp-E0h] BYREF
  DWORD pSessionId; // [rsp+24h] [rbp-DCh] BYREF
  DWORD v15; // [rsp+28h] [rbp-D8h] BYREF
  DWORD v16; // [rsp+2Ch] [rbp-D4h] BYREF
  HMODULE hModule; // [rsp+30h] [rbp-D0h] BYREF
  DWORD idProcess[2048]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR BaseName[264]; // [rsp+2040h] [rbp+1F40h] BYREF

  *a2 = 0;
  cbNeeded = 0;
  if ( !K32EnumProcesses(idProcess, 0x2000u, &cbNeeded) )
    return 0;
  cbNeeded >>= 2;
  if ( cbNeeded > 0x800 )
    cbNeeded = 2048;
  CurrentProcessId = GetCurrentProcessId();
  pSessionId = 0;
  v5 = CurrentProcessId;
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 0;
  v6 = 0;
  for ( i = 0; (unsigned int)i < cbNeeded; i = (unsigned int)(i + 1) )
  {
    v8 = idProcess[i];
    v15 = 0;
    if ( ProcessIdToSessionId(v8, &v15) )
    {
      if ( v15 == pSessionId )
      {
        v9 = idProcess[i];
        if ( v5 != v9 )
        {
          v10 = OpenProcess(0x410u, 0, v9);
          v11 = v10;
          if ( v10 )
          {
            hModule = 0;
            v16 = 0;
            if ( K32EnumProcessModules(v10, &hModule, 8u, &v16)
              && K32GetModuleBaseNameW(v11, hModule, BaseName, 0x104u)
              && !(unsigned int)_o__wcsicmp(BaseName, a1) )
            {
              v6 = idProcess[i];
              *a2 = v11;
              return v6;
            }
            CloseHandle(v11);
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1400187fc  mov     [rsp-8+arg_10], rbx
0x140018801  push    rbp
0x140018802  push    rsi
0x140018803  push    rdi
0x140018804  push    r12
0x140018806  push    r13
0x140018808  push    r14
0x14001880a  push    r15
0x14001880c  lea     rbp, [rsp-2160h]
0x140018814  mov     eax, 2260h
0x140018819  call    _alloca_probe
0x14001881e  sub     rsp, rax
0x140018821  mov     rax, cs:__security_cookie
0x140018828  xor     rax, rsp
0x14001882b  mov     [rbp+2190h+var_40], rax
0x140018832  mov     r12, rdx
0x140018835  mov     qword ptr [rdx], 0
0x14001883c  mov     r13, rcx
0x14001883f  mov     [rsp+2290h+cbNeeded], 0
0x140018847  mov     edx, 2000h; cb
0x14001884c  lea     rcx, [rsp+2290h+idProcess]; lpidProcess
0x140018851  lea     r8, [rsp+2290h+cbNeeded]; lpcbNeeded
0x140018856  call    cs:__imp_K32EnumProcesses
0x14001885d  nop     dword ptr [rax+rax+00h]
0x140018862  test    eax, eax
0x140018864  jz      loc_1400189A7
0x14001886a  mov     eax, [rsp+2290h+cbNeeded]
0x14001886e  mov     ecx, 800h
0x140018873  shr     eax, 2
0x140018876  mov     [rsp+2290h+cbNeeded], eax
0x14001887a  cmp     eax, ecx
0x14001887c  jbe     short loc_140018882
0x14001887e  mov     [rsp+2290h+cbNeeded], ecx
0x140018882  call    cs:__imp_GetCurrentProcessId
0x140018889  nop     dword ptr [rax+rax+00h]
0x14001888e  lea     rdx, [rsp+2290h+pSessionId]; pSessionId
0x140018893  mov     [rsp+2290h+pSessionId], 0
0x14001889b  mov     ecx, eax; dwProcessId
0x14001889d  mov     r15d, eax
0x1400188a0  call    cs:__imp_ProcessIdToSessionId
0x1400188a7  nop     dword ptr [rax+rax+00h]
0x1400188ac  test    eax, eax
0x1400188ae  jz      loc_1400189A7
0x1400188b4  xor     esi, esi
0x1400188b6  xor     ebx, ebx
0x1400188b8  cmp     ebx, [rsp+2290h+cbNeeded]
0x1400188bc  jnb     loc_1400189A3
0x1400188c2  mov     ecx, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1400188c6  lea     rdx, [rsp+2290h+var_2268]; pSessionId
0x1400188cb  mov     [rsp+2290h+var_2268], esi
0x1400188cf  call    cs:__imp_ProcessIdToSessionId
0x1400188d6  nop     dword ptr [rax+rax+00h]
0x1400188db  test    eax, eax
0x1400188dd  jz      loc_140018994
0x1400188e3  mov     eax, [rsp+2290h+pSessionId]
0x1400188e7  cmp     [rsp+2290h+var_2268], eax
0x1400188eb  jnz     loc_140018994
0x1400188f1  mov     r8d, [rsp+rbx*4+2290h+idProcess]; dwProcessId
0x1400188f6  cmp     r15d, r8d
0x1400188f9  jz      loc_140018994
0x1400188ff  xor     edx, edx; bInheritHandle
0x140018901  mov     ecx, 410h; dwDesiredAccess
0x140018906  call    cs:__imp_OpenProcess
0x14001890d  nop     dword ptr [rax+rax+00h]
0x140018912  mov     rdi, rax
0x140018915  test    rax, rax
0x140018918  jz      short loc_140018994
0x14001891a  lea     r9, [rsp+2290h+var_2264]; lpcbNeeded
0x14001891f  mov     [rsp+2290h+hModule], rsi
0x140018924  mov     r8d, 8; cb
0x14001892a  mov     [rsp+2290h+var_2264], esi
0x14001892e  lea     rdx, [rsp+2290h+hModule]; lphModule
0x140018933  mov     rcx, rax; hProcess
0x140018936  call    cs:__imp_K32EnumProcessModules
0x14001893d  nop     dword ptr [rax+rax+00h]
0x140018942  test    eax, eax
0x140018944  jz      short loc_140018985
0x140018946  mov     rdx, [rsp+2290h+hModule]; hModule
0x14001894b  lea     r8, [rbp+2190h+BaseName]; lpBaseName
0x140018952  mov     r9d, 104h; nSize
0x140018958  mov     rcx, rdi; hProcess
0x14001895b  call    cs:__imp_K32GetModuleBaseNameW
0x140018962  nop     dword ptr [rax+rax+00h]
0x140018967  test    eax, eax
0x140018969  jz      short loc_140018985
0x14001896b  mov     rdx, r13
0x14001896e  lea     rcx, [rbp+2190h+BaseName]
0x140018975  call    cs:__imp__o__wcsicmp
0x14001897c  nop     dword ptr [rax+rax+00h]
0x140018981  test    eax, eax
0x140018983  jz      short loc_14001899B
0x140018985  mov     rcx, rdi; hObject
0x140018988  call    cs:__imp_CloseHandle
0x14001898f  nop     dword ptr [rax+rax+00h]
0x140018994  inc     ebx
0x140018996  jmp     loc_1400188B8
0x14001899b  mov     esi, [rsp+rbx*4+2290h+idProcess]
0x14001899f  mov     [r12], rdi
0x1400189a3  mov     eax, esi
0x1400189a5  jmp     short loc_1400189A9
0x1400189a7  xor     eax, eax
0x1400189a9  mov     rcx, [rbp+2190h+var_40]
0x1400189b0  xor     rcx, rsp; StackCookie
0x1400189b3  call    __security_check_cookie
0x1400189b8  mov     rbx, [rsp+2290h+arg_10]
0x1400189c0  add     rsp, 2260h
0x1400189c7  pop     r15
0x1400189c9  pop     r14
0x1400189cb  pop     r13
0x1400189cd  pop     r12
0x1400189cf  pop     rdi
0x1400189d0  pop     rsi
0x1400189d1  pop     rbp
0x1400189d2  retn
```
