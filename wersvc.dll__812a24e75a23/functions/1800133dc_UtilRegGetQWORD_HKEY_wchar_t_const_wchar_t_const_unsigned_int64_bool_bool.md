# UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)

- ea: `0x1800133dc`
- end: `0x18001348e`
- name: `?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z`
- size: `178`
- prototype: `unsigned __int64 __usercall@<rax>(HKEY hKey@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, unsigned __int64@<r9>, bool *, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002d9d8`

## callees

- `0x180007cc8`
- `0x1800133dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013422`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013422`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001347f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001347f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001345d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001345d`

## pseudocode

```c
__int64 __fastcall UtilRegGetQWORD(
        HKEY hKey,
        const wchar_t *a2,
        const wchar_t *a3,
        __int64 a4,
        bool *a5,
        DWORD pcbData)
{
  HKEY *phkResult; // rax
  __int64 v8; // rbx
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF
  __int64 pvData; // [rsp+68h] [rbp+20h] BYREF

  pvData = 0;
  pcbData = 8;
  hkey = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  if ( RegOpenKeyExW(hKey, 0, 0, 0x101u, phkResult)
    || RegGetValueW(hkey, 0, L"CreationTime", 0x40u, 0, &pvData, &pcbData) )
  {
    v8 = 0;
    pvData = 0;
  }
  else
  {
    v8 = pvData;
  }
  if ( hkey )
    RegCloseKey(hkey);
  return v8;
}

```

## disassembly

```asm
0x1800133dc  mov     rax, rsp
0x1800133df  mov     [rax+20h], r9
0x1800133e3  mov     [rax+18h], r8
0x1800133e7  push    rbx
0x1800133e8  sub     rsp, 40h
0x1800133ec  mov     rbx, rcx
0x1800133ef  mov     qword ptr [rax+20h], 0
0x1800133f7  lea     rcx, [rax+18h]
0x1800133fb  mov     dword ptr [rax+30h], 8
0x180013402  mov     qword ptr [rax+18h], 0
0x18001340a  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18001340f  mov     r9d, 101h; samDesired
0x180013415  mov     [rsp+48h+phkResult], rax; phkResult
0x18001341a  xor     r8d, r8d; ulOptions
0x18001341d  xor     edx, edx; lpSubKey
0x18001341f  mov     rcx, rbx; hKey
0x180013422  call    cs:__imp_RegOpenKeyExW
0x180013428  test    eax, eax
0x18001342a  jnz     short loc_18001346E
0x18001342c  mov     rcx, [rsp+48h+hkey]; hkey
0x180013431  lea     rax, [rsp+48h+arg_28]
0x180013436  mov     [rsp+48h+pcbData], rax; pcbData
0x18001343b  lea     r8, Value; "CreationTime"
0x180013442  lea     rax, [rsp+48h+arg_18]
0x180013447  mov     r9d, 40h ; '@'; dwFlags
0x18001344d  mov     [rsp+48h+pvData], rax; pvData
0x180013452  xor     edx, edx; lpSubKey
0x180013454  mov     [rsp+48h+phkResult], 0; pdwType
0x18001345d  call    cs:__imp_RegGetValueW
0x180013463  test    eax, eax
0x180013465  jnz     short loc_18001346E
0x180013467  mov     rbx, [rsp+48h+arg_18]
0x18001346c  jmp     short loc_180013475
0x18001346e  xor     ebx, ebx
0x180013470  mov     [rsp+48h+arg_18], rbx
0x180013475  mov     rcx, [rsp+48h+hkey]; hKey
0x18001347a  test    rcx, rcx
0x18001347d  jz      short loc_180013485
0x18001347f  call    cs:__imp_RegCloseKey
0x180013485  mov     rax, rbx
0x180013488  add     rsp, 40h
0x18001348c  pop     rbx
0x18001348d  retn
```
