# CWinInetHelperClass::LowHealthGetPacFileServerInfo(void)

- ea: `0x180009858`
- end: `0x180009ade`
- name: `?LowHealthGetPacFileServerInfo@CWinInetHelperClass@@AEAAJXZ`
- size: `646`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009ae4`

## callees

- `0x180009858`
- `0x180010450`
- `0x180012d6e`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800098de`
- `KERNEL32!GetLastError` at `0x1800099ac`
- `KERNEL32!GetLastError` at `0x1800098de`
- `KERNEL32!GetLastError` at `0x1800099ac`
- `KERNEL32!GlobalFree` at `0x180009ac3`
- `KERNEL32!GlobalFree` at `0x180009ac3`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x1800098ce`
- `WINHTTP!WinHttpDetectAutoProxyConfigUrl` at `0x1800098ce`
- `WINHTTP!WinHttpCrackUrl` at `0x18000999c`
- `WINHTTP!WinHttpCrackUrl` at `0x18000999c`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::LowHealthGetPacFileServerInfo(CWinInetHelperClass *this)
{
  __int64 v2; // rcx
  signed int LastError; // eax
  signed int v4; // ebx
  LPWSTR v5; // rcx
  _WORD *v6; // r8
  __int64 v7; // rax
  __int64 v8; // rdx
  _WORD *v9; // rcx
  const WCHAR *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  __int64 dwHostNameLength; // rax
  const WCHAR *v14; // rcx
  _WORD *v15; // rax
  __int64 v16; // rcx
  LPSTR lpszHostName; // rdx
  __int64 v18; // r8
  _WORD *v19; // r9
  _WORD *v20; // rdx
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+30h] [rbp-98h] BYREF
  LPWSTR ppwstrAutoConfigUrl; // [rsp+D0h] [rbp+8h] BYREF

  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  v2 = *((_QWORD *)this + 602);
  ppwstrAutoConfigUrl = 0;
  *((_QWORD *)this + 396) = 0;
  if ( v2 )
    (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v2 + 24LL))(
      v2,
      2,
      0,
      L"WinInetHelperClass",
      L"The PAC script cannot be downloaded.");
  if ( !*((_DWORD *)this + 1214) || WinHttpDetectAutoProxyConfigUrl(3u, &ppwstrAutoConfigUrl) )
    goto LABEL_44;
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 >= 0 )
  {
LABEL_44:
    if ( *((_DWORD *)this + 1214) )
    {
      v5 = ppwstrAutoConfigUrl;
      v6 = (_WORD *)((char *)this + 3688);
      v7 = 2147483646;
      v8 = 299;
      do
      {
        if ( !v7 )
          break;
        if ( !*v5 )
          break;
        *v6++ = *v5++;
        --v7;
        --v8;
      }
      while ( v8 );
    }
    else
    {
      v15 = (_WORD *)*((_QWORD *)this + 608);
      if ( !v15 )
      {
LABEL_16:
        UrlComponents.dwStructSize = 104;
        v10 = (const WCHAR *)((char *)this + 3688);
        UrlComponents.dwHostNameLength = -1;
        v11 = -1;
        do
          ++v11;
        while ( v10[v11] );
        if ( WinHttpCrackUrl(v10, v11, 0, &UrlComponents) )
          goto LABEL_22;
        v12 = GetLastError();
        v4 = v12;
        if ( v12 > 0 )
          v4 = (unsigned __int16)v12 | 0x80070000;
        if ( v4 >= 0 )
        {
LABEL_22:
          dwHostNameLength = UrlComponents.dwHostNameLength;
          v14 = (const WCHAR *)((char *)this + 3176);
          if ( UrlComponents.dwHostNameLength <= 0x7FFFFFFEuLL )
          {
            lpszHostName = UrlComponents.lpszHostName;
            v18 = 256;
            v19 = (_WORD *)((char *)this + 3176);
            do
            {
              if ( !dwHostNameLength )
                break;
              if ( !*(_WORD *)lpszHostName )
                break;
              *v19 = *(_WORD *)lpszHostName;
              lpszHostName += 2;
              ++v19;
              --dwHostNameLength;
              --v18;
            }
            while ( v18 );
            v20 = v19 - 1;
            v4 = v18 == 0 ? 0x8007007A : 0;
            if ( v18 )
              v20 = v19;
            *v20 = 0;
            if ( v18 )
            {
              v4 = ExecuteDNSQuery(v14, (unsigned __int16)v20, v18, (struct sockaddr_storage *)((char *)this + 4288));
              if ( v4 >= 0 )
              {
                *((_WORD *)this + 2208) = UrlComponents.nPort;
                *((_DWORD *)this + 793) = 1;
              }
            }
          }
          else
          {
            v4 = -2147024809;
            *v14 = 0;
          }
        }
        goto LABEL_39;
      }
      v16 = 2147483646;
      v6 = (_WORD *)((char *)this + 3688);
      v8 = 299;
      do
      {
        if ( !v16 )
          break;
        if ( !*v15 )
          break;
        *v6++ = *v15++;
        --v16;
        --v8;
      }
      while ( v8 );
    }
    v9 = v6 - 1;
    v4 = v8 == 0 ? 0x8007007A : 0;
    if ( v8 )
      v9 = v6;
    *v9 = 0;
    if ( v8 )
      goto LABEL_16;
  }
LABEL_39:
  if ( ppwstrAutoConfigUrl )
    GlobalFree(ppwstrAutoConfigUrl);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009858  push    rbx
0x18000985a  push    rbp
0x18000985b  push    rsi
0x18000985c  push    rdi
0x18000985d  sub     rsp, 0A8h
0x180009864  xor     edx, edx; Val
0x180009866  mov     rdi, rcx
0x180009869  lea     rcx, [rsp+0C8h+UrlComponents]; void *
0x18000986e  lea     r8d, [rdx+68h]; Size
0x180009872  call    memset_0
0x180009877  mov     rcx, [rdi+12D0h]
0x18000987e  xor     esi, esi
0x180009880  mov     [rsp+0C8h+ppwstrAutoConfigUrl], rsi
0x180009888  mov     [rdi+0C60h], rsi
0x18000988f  test    rcx, rcx
0x180009892  jz      short loc_1800098B9
0x180009894  mov     rax, [rcx]
0x180009897  lea     rdx, aThePacScriptCa; "The PAC script cannot be downloaded."
0x18000989e  mov     [rsp+0C8h+var_A8], rdx
0x1800098a3  lea     r9, aWininethelperc; "WinInetHelperClass"
0x1800098aa  xor     r8d, r8d
0x1800098ad  lea     edx, [rsi+2]
0x1800098b0  mov     rax, [rax+18h]
0x1800098b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098b9  cmp     [rdi+12F8h], esi
0x1800098bf  jz      short loc_180009901
0x1800098c1  lea     rdx, [rsp+0C8h+ppwstrAutoConfigUrl]; ppwstrAutoConfigUrl
0x1800098c9  mov     ecx, 3; dwAutoDetectFlags
0x1800098ce  call    cs:__imp_WinHttpDetectAutoProxyConfigUrl
0x1800098d5  nop     dword ptr [rax+rax+00h]
0x1800098da  test    eax, eax
0x1800098dc  jnz     short loc_180009901
0x1800098de  call    cs:__imp_GetLastError
0x1800098e5  nop     dword ptr [rax+rax+00h]
0x1800098ea  mov     ebx, eax
0x1800098ec  test    eax, eax
0x1800098ee  jle     short loc_1800098F9
0x1800098f0  movzx   ebx, ax
0x1800098f3  or      ebx, 80070000h
0x1800098f9  test    ebx, ebx
0x1800098fb  js      loc_180009AB6
0x180009901  mov     ebp, 7FFFFFFEh
0x180009906  cmp     [rdi+12F8h], esi
0x18000990c  jz      loc_1800099EC
0x180009912  mov     rcx, [rsp+0C8h+ppwstrAutoConfigUrl]
0x18000991a  lea     r8, [rdi+0E68h]
0x180009921  mov     eax, ebp
0x180009923  mov     edx, 12Bh
0x180009928  test    rax, rax
0x18000992b  jz      short loc_18000994C
0x18000992d  movzx   r9d, word ptr [rcx]
0x180009931  test    r9w, r9w
0x180009935  jz      short loc_18000994C
0x180009937  mov     [r8], r9w
0x18000993b  add     rcx, 2
0x18000993f  add     r8, 2
0x180009943  dec     rax
0x180009946  sub     rdx, 1
0x18000994a  jnz     short loc_180009928
0x18000994c  mov     rax, rdx
0x18000994f  lea     rcx, [r8-2]
0x180009953  neg     rax
0x180009956  sbb     ebx, ebx
0x180009958  not     ebx
0x18000995a  and     ebx, 8007007Ah
0x180009960  test    rdx, rdx
0x180009963  cmovnz  rcx, r8
0x180009967  mov     [rcx], si
0x18000996a  jz      loc_180009AB6
0x180009970  mov     [rsp+0C8h+UrlComponents.dwStructSize], 68h ; 'h'
0x180009978  lea     rcx, [rdi+0E68h]; pwszUrl
0x18000997f  mov     [rsp+0C8h+UrlComponents.dwHostNameLength], 0FFFFFFFFh
0x180009987  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000998b  inc     rdx; dwUrlLength
0x18000998e  cmp     [rcx+rdx*2], si
0x180009992  jnz     short loc_18000998B
0x180009994  lea     r9, [rsp+0C8h+UrlComponents]; lpUrlComponents
0x180009999  xor     r8d, r8d; dwFlags
0x18000999c  call    cs:__imp_WinHttpCrackUrl
0x1800099a3  nop     dword ptr [rax+rax+00h]
0x1800099a8  test    eax, eax
0x1800099aa  jnz     short loc_1800099CF
0x1800099ac  call    cs:__imp_GetLastError
0x1800099b3  nop     dword ptr [rax+rax+00h]
0x1800099b8  mov     ebx, eax
0x1800099ba  test    eax, eax
0x1800099bc  jle     short loc_1800099C7
0x1800099be  movzx   ebx, ax
0x1800099c1  or      ebx, 80070000h
0x1800099c7  test    ebx, ebx
0x1800099c9  js      loc_180009AB6
0x1800099cf  mov     eax, [rsp+0C8h+UrlComponents.dwHostNameLength]
0x1800099d3  lea     rcx, [rdi+0C68h]; pNodeName
0x1800099da  cmp     rax, rbp
0x1800099dd  jbe     short loc_180009A3C
0x1800099df  mov     ebx, 80070057h
0x1800099e4  mov     [rcx], si
0x1800099e7  jmp     loc_180009AB6
0x1800099ec  mov     rax, [rdi+1300h]
0x1800099f3  test    rax, rax
0x1800099f6  jz      loc_180009970
0x1800099fc  mov     rcx, rbp
0x1800099ff  lea     r8, [rdi+0E68h]
0x180009a06  mov     edx, 12Bh
0x180009a0b  test    rcx, rcx
0x180009a0e  jz      loc_18000994C
0x180009a14  movzx   r9d, word ptr [rax]
0x180009a18  test    r9w, r9w
0x180009a1c  jz      loc_18000994C
0x180009a22  mov     [r8], r9w
0x180009a26  add     rax, 2
0x180009a2a  add     r8, 2
0x180009a2e  dec     rcx
0x180009a31  sub     rdx, 1
0x180009a35  jnz     short loc_180009A0B
0x180009a37  jmp     loc_18000994C
0x180009a3c  mov     rdx, [rsp+0C8h+UrlComponents.lpszHostName]
0x180009a41  mov     r8d, 100h
0x180009a47  mov     r9, rcx
0x180009a4a  test    rax, rax
0x180009a4d  jz      short loc_180009A6E
0x180009a4f  movzx   r10d, word ptr [rdx]
0x180009a53  test    r10w, r10w
0x180009a57  jz      short loc_180009A6E
0x180009a59  mov     [r9], r10w
0x180009a5d  add     rdx, 2
0x180009a61  add     r9, 2
0x180009a65  dec     rax
0x180009a68  sub     r8, 1; unsigned int
0x180009a6c  jnz     short loc_180009A4A
0x180009a6e  mov     rax, r8
0x180009a71  lea     rdx, [r9-2]
0x180009a75  neg     rax
0x180009a78  sbb     ebx, ebx
0x180009a7a  not     ebx
0x180009a7c  and     ebx, 8007007Ah
0x180009a82  test    r8, r8
0x180009a85  cmovnz  rdx, r9; unsigned __int16
0x180009a89  mov     [rdx], si
0x180009a8c  jz      short loc_180009AB6
0x180009a8e  lea     r9, [rdi+10C0h]; struct sockaddr_storage *
0x180009a95  call    ?ExecuteDNSQuery@@YAJPEBGGKPEAUsockaddr_storage@@@Z; ExecuteDNSQuery(ushort const *,ushort,ulong,sockaddr_storage *)
0x180009a9a  mov     ebx, eax
0x180009a9c  test    eax, eax
0x180009a9e  js      short loc_180009AB6
0x180009aa0  movzx   ecx, [rsp+0C8h+UrlComponents.nPort]
0x180009aa5  mov     [rdi+1140h], cx
0x180009aac  mov     dword ptr [rdi+0C64h], 1
0x180009ab6  mov     rcx, [rsp+0C8h+ppwstrAutoConfigUrl]; hMem
0x180009abe  test    rcx, rcx
0x180009ac1  jz      short loc_180009ACF
0x180009ac3  call    cs:__imp_GlobalFree
0x180009aca  nop     dword ptr [rax+rax+00h]
0x180009acf  mov     eax, ebx
0x180009ad1  add     rsp, 0A8h
0x180009ad8  pop     rdi
0x180009ad9  pop     rsi
0x180009ada  pop     rbp
0x180009adb  pop     rbx
0x180009adc  retn
```
