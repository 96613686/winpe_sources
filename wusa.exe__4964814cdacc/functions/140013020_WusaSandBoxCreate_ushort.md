# WusaSandBoxCreate(ushort * *)

- ea: `0x140013020`
- end: `0x1400131a2`
- name: `?WusaSandBoxCreate@@YAJPEAPEAG@Z`
- size: `386`
- prototype: `__int64 __fastcall(unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x14000f8f0`

## callees

- `0x140001258`
- `0x140001264`
- `0x140001a63`
- `0x14000e280`
- `0x140011dcc`
- `0x140013020`
- `0x140013490`
- `0x140014910`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140013175`
- `KERNEL32!LocalFree` at `0x140013175`
- `KERNEL32!GetSystemDirectoryA` at `0x1400130b4`
- `KERNEL32!GetSystemDirectoryA` at `0x1400130b4`
- `KERNEL32!GetLastError` at `0x1400130f4`
- `KERNEL32!GetLastError` at `0x1400130f4`

## string_xrefs

- `0x1400130e3`: `Failed to create sandbox`
- `0x140013087`: `WusaSandBoxCreate`
- `0x14001311f`: `WusaSandBoxCreate`
- `0x140013161`: `WusaSandBoxCreate`

## pseudocode

```c
__int64 __fastcall WusaSandBoxCreate(unsigned __int16 **a1)
{
  WCHAR *v2; // rax
  WCHAR *v3; // rdi
  signed int v4; // ebx
  signed int LastError; // eax
  HLOCAL v6; // rdi
  CHAR v8; // [rsp+30h] [rbp-138h] BYREF
  __int16 v9; // [rsp+31h] [rbp-137h]
  char v10; // [rsp+33h] [rbp-135h]
  HLOCAL hMem; // [rsp+38h] [rbp-130h] BYREF
  CHAR Buffer[272]; // [rsp+40h] [rbp-128h] BYREF

  v9 = *(_WORD *)":\\";
  *a1 = 0;
  v8 = 99;
  v10 = aC[3];
  v2 = (WCHAR *)operator new(0x208u);
  v3 = v2;
  if ( v2 )
  {
    memset_0(v2, 0, 0x208u);
    if ( GetSystemDirectoryA(Buffer, 0x104u) - 1 > 0x102 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      WusaLogDebugEventA(L"WusaSandBoxCreate", 482, "Failed to get system direcotry");
    }
    else
    {
      v8 = Buffer[0];
      v4 = CreateSandBoxWorker(&v8, v3);
      if ( v4 >= 0 )
      {
        *a1 = v3;
        return (unsigned int)v4;
      }
      WusaLogDebugEventA(L"WusaSandBoxCreate", 488, "Failed to create sandbox");
    }
    operator delete(v3);
  }
  else
  {
    WusaLogDebugEventA(L"WusaSandBoxCreate", 466, "Can't allocate memory for sandbox name");
    v4 = -2147024882;
  }
  hMem = 0;
  WusaGetErrorMessage(v4, (unsigned __int16 **)&hMem);
  v6 = hMem;
  WusaLogDebugEventA(L"WusaSandBoxCreate", 497, "Exit with error code 0X%x (%ls)", v4, (const wchar_t *)hMem);
  if ( v6 )
    LocalFree(v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140013020  mov     [rsp+arg_8], rbx
0x140013025  mov     [rsp+arg_10], rsi
0x14001302a  push    rdi
0x14001302b  sub     rsp, 160h
0x140013032  mov     rax, cs:__security_cookie
0x140013039  xor     rax, rsp
0x14001303c  mov     [rsp+168h+var_18], rax
0x140013044  movzx   eax, word ptr cs:aC+1; ":\\"
0x14001304b  mov     rsi, rcx
0x14001304e  mov     [rsp+168h+var_137], ax
0x140013053  mov     ebx, 208h
0x140013058  mov     al, byte ptr cs:aC+3; ""
0x14001305e  mov     qword ptr [rcx], 0
0x140013065  mov     ecx, ebx; Size
0x140013067  mov     [rsp+168h+var_138], 63h ; 'c'
0x14001306c  mov     [rsp+168h+var_135], al
0x140013070  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140013075  mov     rdi, rax
0x140013078  test    rax, rax
0x14001307b  jnz     short loc_14001309D
0x14001307d  lea     r8, aCanTAllocateMe; "Can't allocate memory for sandbox name"
0x140013084  lea     edx, [rbx-36h]
0x140013087  lea     rcx, aWusasandboxcre; "WusaSandBoxCreate"
0x14001308e  call    WusaLogDebugEventA
0x140013093  mov     ebx, 8007000Eh
0x140013098  jmp     loc_140013133
0x14001309d  mov     r8, rbx; Size
0x1400130a0  xor     edx, edx; Val
0x1400130a2  mov     rcx, rdi; void *
0x1400130a5  call    memset_0
0x1400130aa  mov     edx, 104h; uSize
0x1400130af  lea     rcx, [rsp+168h+Buffer]; lpBuffer
0x1400130b4  call    cs:__imp_GetSystemDirectoryA
0x1400130ba  dec     eax
0x1400130bc  cmp     eax, 102h
0x1400130c1  ja      short loc_1400130F4
0x1400130c3  mov     al, [rsp+168h+Buffer]
0x1400130c7  lea     rcx, [rsp+168h+var_138]
0x1400130cc  mov     rdx, rdi
0x1400130cf  mov     [rsp+168h+var_138], al
0x1400130d3  call    CreateSandBoxWorker
0x1400130d8  mov     ebx, eax
0x1400130da  test    eax, eax
0x1400130dc  jns     short loc_1400130EC
0x1400130de  mov     edx, 1E8h
0x1400130e3  lea     r8, aFailedToCreate_14; "Failed to create sandbox"
0x1400130ea  jmp     short loc_14001311F
0x1400130ec  mov     [rsi], rdi
0x1400130ef  jmp     loc_14001317B
0x1400130f4  call    cs:__imp_GetLastError
0x1400130fa  mov     ebx, eax
0x1400130fc  test    eax, eax
0x1400130fe  jle     short loc_140013109
0x140013100  movzx   ebx, ax
0x140013103  or      ebx, 80070000h
0x140013109  test    ebx, ebx
0x14001310b  lea     r8, aFailedToGetSys; "Failed to get system direcotry"
0x140013112  mov     eax, 80004005h
0x140013117  mov     edx, 1E2h
0x14001311c  cmovns  ebx, eax
0x14001311f  lea     rcx, aWusasandboxcre; "WusaSandBoxCreate"
0x140013126  call    WusaLogDebugEventA
0x14001312b  mov     rcx, rdi; Block
0x14001312e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140013133  lea     rdx, [rsp+168h+hMem]; unsigned __int16 **
0x140013138  mov     [rsp+168h+hMem], 0
0x140013141  mov     ecx, ebx; dwMessageId
0x140013143  call    ?WusaGetErrorMessage@@YAJKPEAPEAG@Z; WusaGetErrorMessage(ulong,ushort * *)
0x140013148  mov     rdi, [rsp+168h+hMem]
0x14001314d  lea     r8, aExitWithErrorC; "Exit with error code 0X%x (%ls)"
0x140013154  mov     r9d, ebx
0x140013157  mov     [rsp+168h+var_148], rdi
0x14001315c  mov     edx, 1F1h
0x140013161  lea     rcx, aWusasandboxcre; "WusaSandBoxCreate"
0x140013168  call    WusaLogDebugEventA
0x14001316d  test    rdi, rdi
0x140013170  jz      short loc_14001317B
0x140013172  mov     rcx, rdi; hMem
0x140013175  call    cs:__imp_LocalFree
0x14001317b  mov     eax, ebx
0x14001317d  mov     rcx, [rsp+168h+var_18]
0x140013185  xor     rcx, rsp; StackCookie
0x140013188  call    __security_check_cookie
0x14001318d  lea     r11, [rsp+168h+var_8]
0x140013195  mov     rbx, [r11+18h]
0x140013199  mov     rsi, [r11+20h]
0x14001319d  mov     rsp, r11
0x1400131a0  pop     rdi
0x1400131a1  retn
```
