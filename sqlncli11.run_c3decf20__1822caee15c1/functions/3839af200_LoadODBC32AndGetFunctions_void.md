# LoadODBC32AndGetFunctions(void)

- ea: `0x3839af200`
- end: `0x3839af39d`
- name: `?LoadODBC32AndGetFunctions@@YAHXZ`
- size: `413`
- prototype: `__int64(void)`
- caller_count: `17`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x3839adba0`
- `0x3839adc50`
- `0x3839add50`
- `0x3839ade50`
- `0x3839adf10`
- `0x3839adfd0`
- `0x3839ae080`
- `0x3839ae290`
- `0x3839ae340`
- `0x3839ae3e0`
- `0x3839ae610`
- `0x3839ae700`
- `0x3839ae8a0`
- `0x3839ae950`
- `0x3839ae9f0`
- `0x3839aead0`
- `0x3839aec30`

## callees

- `0x3838434c0`
- `0x3839af200`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x3839af36e`
- `KERNEL32!FreeLibrary` at `0x3839af36e`
- `KERNEL32!LoadLibraryW` at `0x3839af30e`
- `KERNEL32!LoadLibraryW` at `0x3839af30e`
- `KERNEL32!GetProcAddress` at `0x3839af32a`
- `KERNEL32!GetProcAddress` at `0x3839af345`
- `KERNEL32!GetProcAddress` at `0x3839af32a`
- `KERNEL32!GetProcAddress` at `0x3839af345`
- `KERNEL32!GetSystemDirectoryW` at `0x3839af24a`
- `KERNEL32!GetSystemDirectoryW` at `0x3839af24a`

## string_xrefs

- `0x3839af2c0`: `\odbc32.dll`

## pseudocode

```c
UINT LoadODBC32AndGetFunctions(void)
{
  UINT result; // eax
  WCHAR *v1; // rax
  __int64 v2; // rdx
  int v3; // r10d
  WCHAR *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  char *v7; // r9
  WCHAR v8; // r8
  HMODULE LibraryW; // rax
  __int16 (*ProcAddress)(void *, unsigned __int16, void *, __int16, __int16 *); // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( g_hODBC32Inst )
    return 1;
  result = GetSystemDirectoryW(Buffer, 0x104u);
  if ( result )
  {
    v1 = Buffer;
    v2 = 261;
    while ( *v1 )
    {
      ++v1;
      if ( !--v2 )
        return 0;
    }
    v3 = 0;
    v4 = &Buffer[261 - v2];
    v5 = v2;
    v6 = 0x7FFFFFFF;
    v7 = (char *)((char *)L"\\odbc32.dll" - (char *)v4);
    while ( v6 )
    {
      v8 = *(WCHAR *)((char *)v4 + (_QWORD)v7);
      if ( !v8 )
        break;
      *v4++ = v8;
      --v6;
      if ( !--v5 )
      {
        --v4;
        v3 = -2147024774;
        break;
      }
    }
    *v4 = 0;
    if ( v3 >= 0 )
    {
      LibraryW = LoadLibraryW(Buffer);
      g_hODBC32Inst = LibraryW;
      if ( LibraryW )
      {
        pfnSQLSetConnectAttr = (__int16 (*)(void *, int, void *, int))GetProcAddress(LibraryW, "SQLSetConnectAttr");
        ProcAddress = (__int16 (*)(void *, unsigned __int16, void *, __int16, __int16 *))GetProcAddress(
                                                                                           g_hODBC32Inst,
                                                                                           "SQLGetInfo");
        pfnSQLGetInfo = ProcAddress;
        if ( pfnSQLSetConnectAttr && ProcAddress )
          return 1;
        FreeLibrary(g_hODBC32Inst);
        g_hODBC32Inst = 0;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x3839af200  sub     rsp, 248h
0x3839af207  mov     rax, cs:__security_cookie
0x3839af20e  xor     rax, rsp
0x3839af211  mov     [rsp+248h+var_18], rax
0x3839af219  cmp     cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hODBC32Inst
0x3839af221  jz      short loc_3839AF240
0x3839af223  mov     eax, 1
0x3839af228  mov     rcx, [rsp+248h+var_18]
0x3839af230  xor     rcx, rsp; StackCookie
0x3839af233  call    __security_check_cookie
0x3839af238  add     rsp, 248h
0x3839af23f  retn
0x3839af240  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x3839af245  mov     edx, 104h; uSize
0x3839af24a  call    cs:__imp_GetSystemDirectoryW
0x3839af250  test    eax, eax
0x3839af252  jnz     short loc_3839AF26C
0x3839af254  mov     rcx, [rsp+248h+var_18]
0x3839af25c  xor     rcx, rsp; StackCookie
0x3839af25f  call    __security_check_cookie
0x3839af264  add     rsp, 248h
0x3839af26b  retn
0x3839af26c  mov     ecx, 105h
0x3839af271  lea     rax, [rsp+248h+Buffer]
0x3839af276  mov     [rsp+248h+var_8], rbx
0x3839af27e  mov     edx, ecx
0x3839af280  cmp     word ptr [rax], 0
0x3839af284  jz      short loc_3839AF294
0x3839af286  add     rax, 2
0x3839af28a  dec     rdx
0x3839af28d  jnz     short loc_3839AF280
0x3839af28f  jmp     loc_3839AF37B
0x3839af294  test    rdx, rdx
0x3839af297  jz      loc_3839AF37B
0x3839af29d  mov     r8, rcx
0x3839af2a0  lea     rax, [rsp+248h+Buffer]
0x3839af2a5  mov     ebx, 0
0x3839af2aa  sub     r8, rdx
0x3839af2ad  mov     r10d, ebx
0x3839af2b0  lea     rax, [rax+r8*2]
0x3839af2b4  sub     rcx, r8
0x3839af2b7  jz      short loc_3839AF2F7
0x3839af2b9  lea     rdx, [r8+7FFFFEFAh]
0x3839af2c0  lea     r9, aOdbc32Dll; "\\odbc32.dll"
0x3839af2c7  add     rdx, rcx
0x3839af2ca  sub     r9, rax
0x3839af2cd  nop     dword ptr [rax]
0x3839af2d0  test    rdx, rdx
0x3839af2d3  jz      short loc_3839AF2F2
0x3839af2d5  movzx   r8d, word ptr [r9+rax]
0x3839af2da  test    r8w, r8w
0x3839af2de  jz      short loc_3839AF2F2
0x3839af2e0  mov     [rax], r8w
0x3839af2e4  add     rax, 2
0x3839af2e8  dec     rdx
0x3839af2eb  dec     rcx
0x3839af2ee  jnz     short loc_3839AF2D0
0x3839af2f0  jmp     short loc_3839AF2F7
0x3839af2f2  test    rcx, rcx
0x3839af2f5  jnz     short loc_3839AF301
0x3839af2f7  sub     rax, 2
0x3839af2fb  mov     r10d, 8007007Ah
0x3839af301  mov     [rax], bx
0x3839af304  test    r10d, r10d
0x3839af307  js      short loc_3839AF37B
0x3839af309  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x3839af30e  call    cs:__imp_LoadLibraryW
0x3839af314  mov     cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hODBC32Inst
0x3839af31b  test    rax, rax
0x3839af31e  jz      short loc_3839AF37B
0x3839af320  lea     rdx, aSqlsetconnecta_0; "SQLSetConnectAttr"
0x3839af327  mov     rcx, rax; hModule
0x3839af32a  call    cs:__imp_GetProcAddress
0x3839af330  mov     rcx, cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA; hModule
0x3839af337  lea     rdx, aSqlgetinfo; "SQLGetInfo"
0x3839af33e  mov     cs:?pfnSQLSetConnectAttr@@3P6AFPEAXJ0J@ZEA, rax; short (*pfnSQLSetConnectAttr)(void *,long,void *,long)
0x3839af345  call    cs:__imp_GetProcAddress
0x3839af34b  cmp     cs:?pfnSQLSetConnectAttr@@3P6AFPEAXJ0J@ZEA, rbx; short (*pfnSQLSetConnectAttr)(void *,long,void *,long)
0x3839af352  mov     cs:?pfnSQLGetInfo@@3P6AFPEAXG0FPEAF@ZEA, rax; short (*pfnSQLGetInfo)(void *,ushort,void *,short,short *)
0x3839af359  jz      short loc_3839AF367
0x3839af35b  test    rax, rax
0x3839af35e  jz      short loc_3839AF367
0x3839af360  mov     eax, 1
0x3839af365  jmp     short loc_3839AF37D
0x3839af367  mov     rcx, cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA; hLibModule
0x3839af36e  call    cs:__imp_FreeLibrary
0x3839af374  mov     cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hODBC32Inst
0x3839af37b  xor     eax, eax
0x3839af37d  mov     rbx, [rsp+248h+var_8]
0x3839af385  mov     rcx, [rsp+248h+var_18]
0x3839af38d  xor     rcx, rsp; StackCookie
0x3839af390  call    __security_check_cookie
0x3839af395  add     rsp, 248h
0x3839af39c  retn
```
