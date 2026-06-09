# IIS_VDIR::InitializeStatic(void)

- ea: `0x18001ccc0`
- end: `0x18001cdc9`
- name: `?InitializeStatic@IIS_VDIR@@SAJXZ`
- size: `265`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000806c`

## callees

- `0x1800011d4`
- `0x180001214`
- `0x18001ccc0`
- `0x180022304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ccea`
- `iisutil!PuDbgPrint` at `0x18001cd33`
- `iisutil!PuDbgPrint` at `0x18001cd33`
- `ADVAPI32!CryptReleaseContext` at `0x18001cdb0`
- `ADVAPI32!CryptReleaseContext` at `0x18001cdb0`
- `ADVAPI32!CryptAcquireContextW` at `0x18001cce0`
- `ADVAPI32!CryptAcquireContextW` at `0x18001cce0`

## string_xrefs

- `0x18001cd2c`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18001cd1a`: `TOKEN_KEY::Initialize`

## pseudocode

```c
__int64 IIS_VDIR::InitializeStatic(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  wchar_t *v2; // rax
  wchar_t *v3; // rcx

  if ( CryptAcquireContextW(&TOKEN_KEY::sm_hCryptProv, 0, 0, 0x18u, 0xF0000000) )
    goto LABEL_7;
  LastError = GetLastError();
  v1 = LastError;
  if ( LastError > 0 )
    v1 = (unsigned __int16)LastError | 0x80070000;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
      982,
      "TOKEN_KEY::Initialize",
      "CryptAcquireContext() failed. hr = 0x%x\n",
      v1);
  if ( v1 >= 0 )
  {
LABEL_7:
    v2 = (wchar_t *)operator new(0xA0Cu);
    if ( v2 )
    {
      IIS_VDIR::sm_LogonProvider = v2;
      *v2 = 0;
      v2[256] = 0;
      *((_QWORD *)v2 + 320) = 0;
      *((_DWORD *)v2 + 642) = 0;
      v1 = IIS_LOGON_PROVIDER::InitializeInstance(0);
      if ( v1 >= 0 )
        return (unsigned int)v1;
      v3 = IIS_VDIR::sm_LogonProvider;
    }
    else
    {
      v3 = 0;
      v1 = -2147024888;
      IIS_VDIR::sm_LogonProvider = 0;
    }
    operator delete(v3);
    IIS_VDIR::sm_LogonProvider = 0;
    if ( TOKEN_KEY::sm_hCryptProv )
    {
      CryptReleaseContext(TOKEN_KEY::sm_hCryptProv, 0);
      TOKEN_KEY::sm_hCryptProv = 0;
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001ccc0  push    rbx
0x18001ccc2  sub     rsp, 30h
0x18001ccc6  mov     r9d, 18h; dwProvType
0x18001cccc  mov     [rsp+38h+dwFlags], 0F0000000h; dwFlags
0x18001ccd4  xor     r8d, r8d; szProvider
0x18001ccd7  lea     rcx, ?sm_hCryptProv@TOKEN_KEY@@0_KA; phProv
0x18001ccde  xor     edx, edx; szContainer
0x18001cce0  call    cs:__imp_CryptAcquireContextW
0x18001cce6  test    eax, eax
0x18001cce8  jnz     short loc_18001CD41
0x18001ccea  call    cs:__imp_GetLastError
0x18001ccf0  mov     ebx, eax
0x18001ccf2  test    eax, eax
0x18001ccf4  jle     short loc_18001CCFF
0x18001ccf6  movzx   ebx, ax
0x18001ccf9  or      ebx, 80070000h
0x18001ccff  test    byte ptr cs:g_dwDebugFlags, 3
0x18001cd06  jz      short loc_18001CD39
0x18001cd08  mov     rcx, cs:g_pDebug
0x18001cd0f  lea     rax, aCryptacquireco; "CryptAcquireContext() failed. hr = 0x%x"...
0x18001cd16  mov     [rsp+38h+var_10], ebx
0x18001cd1a  lea     r9, aTokenKeyInitia; "TOKEN_KEY::Initialize"
0x18001cd21  mov     r8d, 3D6h
0x18001cd27  mov     qword ptr [rsp+38h+dwFlags], rax
0x18001cd2c  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001cd33  call    cs:__imp_PuDbgPrint
0x18001cd39  test    ebx, ebx
0x18001cd3b  js      loc_18001CDC1
0x18001cd41  mov     ecx, 0A0Ch; Size
0x18001cd46  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cd4b  test    rax, rax
0x18001cd4e  jz      short loc_18001CD84
0x18001cd50  xor     ecx, ecx; this
0x18001cd52  mov     cs:?sm_LogonProvider@IIS_VDIR@@0PEAVIIS_LOGON_PROVIDER@@EA, rax; IIS_LOGON_PROVIDER * IIS_VDIR::sm_LogonProvider
0x18001cd59  mov     [rax], cx
0x18001cd5c  mov     [rax+200h], cx
0x18001cd63  mov     [rax+0A00h], rcx
0x18001cd6a  mov     [rax+0A08h], ecx
0x18001cd70  call    ?InitializeInstance@IIS_LOGON_PROVIDER@@QEAAJXZ; IIS_LOGON_PROVIDER::InitializeInstance(void)
0x18001cd75  mov     ebx, eax
0x18001cd77  test    eax, eax
0x18001cd79  jns     short loc_18001CDC1
0x18001cd7b  mov     rcx, cs:?sm_LogonProvider@IIS_VDIR@@0PEAVIIS_LOGON_PROVIDER@@EA; IIS_LOGON_PROVIDER * IIS_VDIR::sm_LogonProvider
0x18001cd82  jmp     short loc_18001CD92
0x18001cd84  xor     ecx, ecx; Block
0x18001cd86  mov     ebx, 80070008h
0x18001cd8b  mov     cs:?sm_LogonProvider@IIS_VDIR@@0PEAVIIS_LOGON_PROVIDER@@EA, rcx; IIS_LOGON_PROVIDER * IIS_VDIR::sm_LogonProvider
0x18001cd92  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001cd97  mov     rcx, cs:?sm_hCryptProv@TOKEN_KEY@@0_KA; hProv
0x18001cd9e  mov     cs:?sm_LogonProvider@IIS_VDIR@@0PEAVIIS_LOGON_PROVIDER@@EA, 0; IIS_LOGON_PROVIDER * IIS_VDIR::sm_LogonProvider
0x18001cda9  test    rcx, rcx
0x18001cdac  jz      short loc_18001CDC1
0x18001cdae  xor     edx, edx; dwFlags
0x18001cdb0  call    cs:__imp_CryptReleaseContext
0x18001cdb6  mov     cs:?sm_hCryptProv@TOKEN_KEY@@0_KA, 0; unsigned __int64 TOKEN_KEY::sm_hCryptProv
0x18001cdc1  mov     eax, ebx
0x18001cdc3  add     rsp, 30h
0x18001cdc7  pop     rbx
0x18001cdc8  retn
```
