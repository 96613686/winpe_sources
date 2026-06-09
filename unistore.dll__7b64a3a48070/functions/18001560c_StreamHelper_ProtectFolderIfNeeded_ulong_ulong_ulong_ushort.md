# StreamHelper::ProtectFolderIfNeeded(ulong,ulong,ulong,ushort *)

- ea: `0x18001560c`
- end: `0x180015787`
- name: `?ProtectFolderIfNeeded@StreamHelper@@KAJKKKPEAG@Z`
- size: `379`
- prototype: `static int(unsigned int, unsigned int, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013894`

## callees

- `0x180013524`
- `0x18001560c`
- `0x180015ee0`
- `0x1800721ec`
- `0x180072eec`
- `0x1800ba22c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015742`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800156f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180015691`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180015691`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x18001575a`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x18001575a`

## pseudocode

```c
__int64 __fastcall StreamHelper::ProtectFolderIfNeeded(unsigned int a1, unsigned int a2, int a3, unsigned __int16 *a4)
{
  unsigned int StoreProtectedProps; // eax
  __int64 v6; // r8
  DPHelper **v7; // rbx
  int v8; // eax
  const unsigned __int16 *v9; // r8
  unsigned int v10; // edi
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  signed int LastError; // eax
  __int64 v18; // r8
  int v19; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-18h] BYREF
  int v21; // [rsp+60h] [rbp+18h] BYREF

  v21 = a3;
  if ( g_fDoProtectionCheck )
  {
    v21 = 0;
    hMem = 0;
    StoreProtectedProps = DBManager::GetStoreProtectedProps(a1, a2, (struct _USPROPVAL **)&hMem, &v21);
    if ( (int)(StoreProtectedProps + 0x80000000) >= 0 && StoreProtectedProps != -2147024871 )
      Log_UnistoreHREvent_17(StoreProtectedProps, 0, v6, 388);
    if ( v21 )
    {
      v7 = (DPHelper **)hMem;
      v8 = StringCchPrintfW(a4, 0x104u, L"%s%s\\", a4, *((_QWORD *)hMem + 4));
      v10 = v8;
      if ( v8 < 0 )
      {
        v12 = 392;
      }
      else
      {
        if ( PathFileExistsW(a4) )
        {
LABEL_6:
          v10 = 0;
LABEL_7:
          LocalFree(v7);
          return v10;
        }
        LastError = GetLastError();
        v10 = LastError;
        if ( (unsigned int)(LastError - 2) > 1 )
        {
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          Log_UnistoreHREvent_17(v10, 0, v18, 402);
          if ( !v10 )
            Log_AssertionEvent_1(v16, v15, 402);
          goto LABEL_7;
        }
        v19 = SHCreateDirectoryExW(0, a4, 0);
        v10 = v19;
        if ( v19 )
        {
          if ( v19 > 0 )
            v10 = (unsigned __int16)v19 | 0x80070000;
          v13 = 0;
          v12 = 406;
          v14 = v10;
          goto LABEL_12;
        }
        v8 = DPHelper::ProtectFile(v7[1], a4, v9);
        v10 = v8;
        if ( v8 >= 0 )
          goto LABEL_6;
        v12 = 409;
      }
      v13 = 1;
      v14 = (unsigned int)v8;
LABEL_12:
      Log_UnistoreHREvent_17(v14, v13, v9, v12);
      goto LABEL_7;
    }
    if ( hMem )
      LocalFree(hMem);
  }
  return 0;
}

```

## disassembly

```asm
0x18001560c  mov     rax, rsp
0x18001560f  mov     [rax+8], rbx
0x180015613  mov     [rax+10h], rsi
0x180015617  mov     [rax+18h], r8d
0x18001561b  push    rdi
0x18001561c  sub     rsp, 40h
0x180015620  cmp     cs:?g_fDoProtectionCheck@@3HA, 0; int g_fDoProtectionCheck
0x180015627  mov     rsi, r9
0x18001562a  jz      loc_1800156F8
0x180015630  lea     r9, [rax+18h]; int *
0x180015634  mov     dword ptr [rax+18h], 0
0x18001563b  lea     r8, [rax-18h]; struct _USPROPVAL **
0x18001563f  mov     qword ptr [rax-18h], 0
0x180015647  call    ?GetStoreProtectedProps@DBManager@@SAJKKPEAPEAU_USPROPVAL@@PEAH@Z; DBManager::GetStoreProtectedProps(ulong,ulong,_USPROPVAL * *,int *)
0x18001564c  mov     edx, 80000000h
0x180015651  lea     ecx, [rax+rdx]
0x180015654  test    edx, ecx
0x180015656  jz      short loc_1800156BC
0x180015658  cmp     [rsp+48h+arg_10], 0
0x18001565d  jz      loc_1800156E8
0x180015663  mov     rbx, [rsp+48h+hMem]
0x180015668  lea     r8, aSS; "%s%s\\"
0x18001566f  mov     r9, rsi
0x180015672  mov     edx, 104h; unsigned __int64
0x180015677  mov     rcx, rsi; unsigned __int16 *
0x18001567a  mov     rax, [rbx+20h]
0x18001567e  mov     [rsp+48h+var_28], rax
0x180015683  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015688  mov     edi, eax
0x18001568a  test    eax, eax
0x18001568c  js      short loc_1800156D4
0x18001568e  mov     rcx, rsi; pszPath
0x180015691  call    cs:__imp_PathFileExistsW
0x180015697  test    eax, eax
0x180015699  jz      loc_180015742
0x18001569f  xor     edi, edi
0x1800156a1  mov     rcx, rbx; hMem
0x1800156a4  call    cs:__imp_LocalFree
0x1800156aa  mov     eax, edi
0x1800156ac  mov     rbx, [rsp+48h+arg_0]
0x1800156b1  mov     rsi, [rsp+48h+arg_8]
0x1800156b6  add     rsp, 40h
0x1800156ba  pop     rdi
0x1800156bb  retn
0x1800156bc  cmp     eax, 80070019h
0x1800156c1  jz      short loc_180015658
0x1800156c3  xor     edx, edx
0x1800156c5  mov     r9d, 184h
0x1800156cb  mov     ecx, eax
0x1800156cd  call    Log_UnistoreHREvent_17
0x1800156d2  jmp     short loc_180015658
0x1800156d4  mov     r9d, 188h
0x1800156da  mov     edx, 1
0x1800156df  mov     ecx, eax
0x1800156e1  call    Log_UnistoreHREvent_17
0x1800156e6  jmp     short loc_1800156A1
0x1800156e8  mov     rcx, [rsp+48h+hMem]; hMem
0x1800156ed  test    rcx, rcx
0x1800156f0  jz      short loc_1800156F8
0x1800156f2  call    cs:__imp_LocalFree
0x1800156f8  xor     eax, eax
0x1800156fa  jmp     short loc_1800156AC
0x1800156fc  test    eax, eax
0x1800156fe  jle     short loc_180015709
0x180015700  movzx   edi, ax
0x180015703  or      edi, 80070000h
0x180015709  mov     esi, 192h
0x18001570e  xor     edx, edx
0x180015710  mov     r9d, esi
0x180015713  mov     ecx, edi
0x180015715  call    Log_UnistoreHREvent_17
0x18001571a  test    edi, edi
0x18001571c  jnz     short loc_1800156A1
0x18001571e  mov     r8d, esi
0x180015721  call    Log_AssertionEvent_1
0x180015726  jmp     loc_1800156A1
0x18001572b  jle     short loc_180015736
0x18001572d  movzx   edi, ax
0x180015730  or      edi, 80070000h
0x180015736  xor     edx, edx
0x180015738  mov     r9d, 196h
0x18001573e  mov     ecx, edi
0x180015740  jmp     short loc_1800156E1
0x180015742  call    cs:__imp_GetLastError
0x180015748  mov     edi, eax
0x18001574a  lea     ecx, [rax-2]
0x18001574d  cmp     ecx, 1
0x180015750  ja      short loc_1800156FC
0x180015752  xor     r8d, r8d; psa
0x180015755  mov     rdx, rsi; pszPath
0x180015758  xor     ecx, ecx; hwnd
0x18001575a  call    cs:__imp_SHCreateDirectoryExW
0x180015760  mov     edi, eax
0x180015762  test    eax, eax
0x180015764  jnz     short loc_18001572B
0x180015766  mov     rcx, [rbx+8]; this
0x18001576a  mov     rdx, rsi; unsigned __int16 *
0x18001576d  call    ?ProtectFile@DPHelper@@YAJPEBG0@Z; DPHelper::ProtectFile(ushort const *,ushort const *)
0x180015772  mov     edi, eax
0x180015774  test    eax, eax
0x180015776  jns     loc_18001569F
0x18001577c  mov     r9d, 199h
0x180015782  jmp     loc_1800156DA
```
