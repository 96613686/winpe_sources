# _CatAdminSetupDefaults(void)

- ea: `0x1800213f0`
- end: `0x1800214e7`
- name: `?_CatAdminSetupDefaults@@YAHXZ`
- size: `247`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180021378`

## callees

- `0x180005d00`
- `0x180005f00`
- `0x1800213f0`
- `0x18002c760`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800214d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800214d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180021426`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180021426`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002140b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18002140b`

## pseudocode

```c
__int64 _CatAdminSetupDefaults(void)
{
  unsigned __int16 *v0; // rcx
  unsigned int v1; // ebx
  unsigned int v3; // r8d
  int v4; // [rsp+20h] [rbp-238h]
  int v5; // [rsp+28h] [rbp-230h]
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !(unsigned __int8)RtlIsStateSeparationEnabled() || !(unsigned int)_CatAdminSetupPersistedDefaults() )
  {
    Buffer[0] = 0;
    if ( GetSystemDirectoryW(Buffer, 0x104u) )
    {
      v1 = 1;
      hMem = _CatAdminCreatePath(Buffer, L"CatRoot", 1);
      if ( hMem )
      {
        qword_180069EB8 = _CatAdminCreatePath(Buffer, L"CatRoot2", 1);
        if ( qword_180069EB8 )
          return v1;
        v3 = 2316;
      }
      else
      {
        v3 = 2303;
      }
    }
    else
    {
      v3 = 2290;
    }
    ErrLog_LogError(v0, 2u, v3, 0, v4, v5);
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800213f0  push    rbx
0x1800213f2  sub     rsp, 250h
0x1800213f9  mov     rax, cs:__security_cookie
0x180021400  xor     rax, rsp
0x180021403  mov     [rsp+258h+var_18], rax
0x18002140b  call    cs:__imp_RtlIsStateSeparationEnabled
0x180021411  test    al, al
0x180021413  jnz     short loc_180021490
0x180021415  xor     eax, eax
0x180021417  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x18002141c  mov     edx, 104h; uSize
0x180021421  mov     [rsp+258h+Buffer], ax
0x180021426  call    cs:__imp_GetSystemDirectoryW
0x18002142c  test    eax, eax
0x18002142e  jz      short loc_1800214A4
0x180021430  mov     ebx, 1
0x180021435  lea     rdx, aCatroot_0; "CatRoot"
0x18002143c  mov     r8d, ebx; int
0x18002143f  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x180021444  call    ?_CatAdminCreatePath@@YAPEAGPEBG0H@Z; _CatAdminCreatePath(ushort const *,ushort const *,int)
0x180021449  mov     cs:hMem, rax
0x180021450  test    rax, rax
0x180021453  jz      short loc_1800214AC
0x180021455  mov     r8d, ebx; int
0x180021458  lea     rdx, aCatroot2_0; "CatRoot2"
0x18002145f  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x180021464  call    ?_CatAdminCreatePath@@YAPEAGPEBG0H@Z; _CatAdminCreatePath(ushort const *,ushort const *,int)
0x180021469  mov     cs:qword_180069EB8, rax
0x180021470  test    rax, rax
0x180021473  jz      short loc_1800214B4
0x180021475  mov     eax, ebx
0x180021477  mov     rcx, [rsp+258h+var_18]
0x18002147f  xor     rcx, rsp; StackCookie
0x180021482  call    __security_check_cookie
0x180021487  add     rsp, 250h
0x18002148e  pop     rbx
0x18002148f  retn
0x180021490  call    ?_CatAdminSetupPersistedDefaults@@YAHXZ; _CatAdminSetupPersistedDefaults(void)
0x180021495  test    eax, eax
0x180021497  jz      loc_180021415
0x18002149d  mov     eax, 1
0x1800214a2  jmp     short loc_180021477
0x1800214a4  mov     r8d, 8F2h
0x1800214aa  jmp     short loc_1800214BA
0x1800214ac  mov     r8d, 8FFh
0x1800214b2  jmp     short loc_1800214BA
0x1800214b4  mov     r8d, 90Ch; unsigned int
0x1800214ba  xor     r9d, r9d; unsigned int
0x1800214bd  lea     edx, [r9+2]; unsigned int
0x1800214c1  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x1800214c6  mov     rcx, cs:hMem; hMem
0x1800214cd  test    rcx, rcx
0x1800214d0  jz      short loc_1800214E3
0x1800214d2  call    cs:__imp_LocalFree
0x1800214d8  mov     cs:hMem, 0
0x1800214e3  xor     ebx, ebx
0x1800214e5  jmp     short loc_180021475
```
