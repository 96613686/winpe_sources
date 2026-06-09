# InitMskeyprotectModule(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x18006aa70`
- end: `0x18006ab2d`
- name: `?InitMskeyprotectModule@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `189`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180057c8c`
- `0x18006aa70`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006aa83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006aa83`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006aaa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006aae3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006aaa3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006aae3`

## string_xrefs

- `0x18006aa76`: `mskeyprotect.dll`

## pseudocode

```c
__int64 __fastcall InitMskeyprotectModule(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  HMODULE Library; // rax
  CCipherMill *v4; // rcx
  __int64 v5; // rdx

  Library = LoadLibraryExW(L"mskeyprotect.dll", 0, 0x800u);
  g_hMskeyprotect = Library;
  if ( Library )
  {
    g_pKeyFileProtectSessionTicket = (unsigned int (*)(unsigned __int8 *, unsigned int, const unsigned __int16 *, unsigned __int8 **, unsigned int *))GetProcAddress(Library, "KeyFileProtectSessionTicket");
    if ( g_pKeyFileProtectSessionTicket )
    {
      g_pKeyFileUnprotectSessionTicket = (unsigned int (*)(unsigned __int8 *, unsigned int, const unsigned __int16 *, unsigned __int8 **, unsigned int *))GetProcAddress(g_hMskeyprotect, "KeyFileUnprotectSessionTicket");
      if ( !g_pKeyFileUnprotectSessionTicket )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v5 = 11;
          goto LABEL_10;
        }
      }
    }
    else
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CCipherMill *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 10;
LABEL_10:
        WPP_SF_(*((_QWORD *)v4 + 2), v5, WPP_b032270e2095315efa9e144016cb8858_Traceguids);
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18006aa70  sub     rsp, 28h
0x18006aa74  xor     edx, edx; hFile
0x18006aa76  lea     rcx, aMskeyprotectDl; "mskeyprotect.dll"
0x18006aa7d  mov     r8d, 800h; dwFlags
0x18006aa83  call    cs:__imp_LoadLibraryExW
0x18006aa89  mov     cs:?g_hMskeyprotect@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hMskeyprotect
0x18006aa90  test    rax, rax
0x18006aa93  jz      loc_18006AB23
0x18006aa99  lea     rdx, aKeyfileprotect; "KeyFileProtectSessionTicket"
0x18006aaa0  mov     rcx, rax; hModule
0x18006aaa3  call    cs:__imp_GetProcAddress
0x18006aaa9  mov     cs:?g_pKeyFileProtectSessionTicket@@3P6AKPEAEKPEBGPEAPEAEPEAK@ZEA, rax; ulong (*g_pKeyFileProtectSessionTicket)(uchar *,ulong,ushort const *,uchar * *,ulong *)
0x18006aab0  test    rax, rax
0x18006aab3  jnz     short loc_18006AAD5
0x18006aab5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aabc  lea     rax, WPP_GLOBAL_Control
0x18006aac3  cmp     rcx, rax
0x18006aac6  jz      short loc_18006AB23
0x18006aac8  test    byte ptr [rcx+1Ch], 1
0x18006aacc  jz      short loc_18006AB23
0x18006aace  mov     edx, 0Ah
0x18006aad3  jmp     short loc_18006AB13
0x18006aad5  mov     rcx, cs:?g_hMskeyprotect@@3PEAUHINSTANCE__@@EA; hModule
0x18006aadc  lea     rdx, aKeyfileunprote; "KeyFileUnprotectSessionTicket"
0x18006aae3  call    cs:__imp_GetProcAddress
0x18006aae9  mov     cs:?g_pKeyFileUnprotectSessionTicket@@3P6AKPEAEKPEBGPEAPEAEPEAK@ZEA, rax; ulong (*g_pKeyFileUnprotectSessionTicket)(uchar *,ulong,ushort const *,uchar * *,ulong *)
0x18006aaf0  test    rax, rax
0x18006aaf3  jnz     short loc_18006AB23
0x18006aaf5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006aafc  lea     rax, WPP_GLOBAL_Control
0x18006ab03  cmp     rcx, rax
0x18006ab06  jz      short loc_18006AB23
0x18006ab08  test    byte ptr [rcx+1Ch], 1
0x18006ab0c  jz      short loc_18006AB23
0x18006ab0e  mov     edx, 0Bh
0x18006ab13  mov     rcx, [rcx+10h]
0x18006ab17  lea     r8, WPP_b032270e2095315efa9e144016cb8858_Traceguids
0x18006ab1e  call    WPP_SF_
0x18006ab23  mov     eax, 1
0x18006ab28  add     rsp, 28h
0x18006ab2c  retn
```
