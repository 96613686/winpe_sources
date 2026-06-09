# Sm_Shiloh::LoadDll(_NLFunctionTable *)

- ea: `0x383ac8520`
- end: `0x383ac880f`
- name: `?LoadDll@Sm_Shiloh@@CAKPEAU_NLFunctionTable@@@Z`
- size: `751`
- prototype: `unsigned int __fastcall(struct _NLFunctionTable *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x383ac8a60`

## callees

- `0x383846430`
- `0x383892180`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ab0c30`
- `0x383ac8520`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x383ac877d`
- `KERNEL32!FreeLibrary` at `0x383ac877d`
- `KERNEL32!GetLastError` at `0x383ac85d3`
- `KERNEL32!GetLastError` at `0x383ac8712`
- `KERNEL32!GetLastError` at `0x383ac85d3`
- `KERNEL32!GetLastError` at `0x383ac8712`
- `KERNEL32!GetProcAddress` at `0x383ac8638`
- `KERNEL32!GetProcAddress` at `0x383ac8638`

## string_xrefs

- `0x383ac857f`: `ConnectionOpen`
- `0x383ac8597`: `ConnectionWrite`
- `0x383ac858b`: `ConnectionRead`
- `0x383ac85bb`: `dbmslpcn.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Sm_Shiloh::LoadDll(struct _NLFunctionTable *a1)
{
  HMODULE v2; // rax
  DWORD LastError; // ebx
  __int64 v4; // r8
  __int64 v5; // rbx
  FARPROC ProcAddress; // rax
  LPCSTR lpProcName[6]; // [rsp+38h] [rbp-70h]
  _QWORD v9[8]; // [rsp+68h] [rbp-40h]
  __int64 v10; // [rsp+B8h] [rbp+10h] BYREF

  v10 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48E28[0] )
    bidScopeEnterA(&v10, off_383B48E28[0], a1);
  lpProcName[0] = "ConnectionObjectSize";
  lpProcName[1] = "ConnectionOpen";
  lpProcName[2] = "ConnectionRead";
  lpProcName[3] = "ConnectionWrite";
  lpProcName[4] = "ConnectionClose";
  lpProcName[5] = "ConnectionCheckForData";
  v2 = SNILoadSystemLibA("dbmslpcn.dll");
  hModule = v2;
  if ( v2 )
  {
    v5 = 0;
    while ( 1 )
    {
      ProcAddress = GetProcAddress(v2, lpProcName[v5]);
      v9[v5] = ProcAddress;
      if ( !ProcAddress )
        break;
      if ( ++v5 >= 6 )
      {
        *(_QWORD *)a1 = v9[0];
        *((_QWORD *)a1 + 1) = v9[1];
        *((_QWORD *)a1 + 2) = v9[2];
        *((_QWORD *)a1 + 3) = v9[3];
        *((_QWORD *)a1 + 4) = v9[4];
        *((_QWORD *)a1 + 5) = v9[5];
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48178[0] )
          bidTraceA(off_383B45AF8[0], 69632, off_383B48178[0], 0);
        if ( v10 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
          off_383B15058();
        return 0;
      }
      v2 = hModule;
    }
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B48180[0] )
    {
      SniErrorIdFromStringId(0xC3D9u);
      bidTraceA(off_383B45B00[0], 62464, off_383B48180[0], 4);
    }
    v4 = 50137;
  }
  else
  {
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_383B48188[0] )
    {
      SniErrorIdFromStringId(0xC3D8u);
      bidTraceA(off_383B45B08[0], 52224, off_383B48188[0], 4);
    }
    v4 = 50136;
  }
  SNISetLastError(4, LastError, v4);
  if ( hModule )
    FreeLibrary(hModule);
  hModule = 0;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48170[0] )
    bidTraceA(off_383B45AF0[0], 79872, off_383B48170[0], LastError);
  if ( v10 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return LastError;
}

```

## disassembly

```asm
0x383ac8520  mov     r11, rsp
0x383ac8523  push    rdi
0x383ac8524  sub     rsp, 0A0h
0x383ac852b  mov     qword ptr [r11-78h], 0FFFFFFFFFFFFFFFEh
0x383ac8533  mov     [r11+8], rbx
0x383ac8537  mov     rdi, rcx
0x383ac853a  mov     qword ptr [r11+10h], 0FFFFFFFFFFFFFFFFh
0x383ac8542  mov     eax, cs:_bidGblFlags
0x383ac8548  and     eax, 20004h
0x383ac854d  cmp     eax, 20004h
0x383ac8552  jnz     short loc_383AC8573
0x383ac8554  mov     rax, cs:off_383B48E28; "<Sm_Shiloh::LoadDll|API|SNI> pFuncs: %p"...
0x383ac855b  test    rax, rax
0x383ac855e  jz      short loc_383AC8573
0x383ac8560  mov     r8, rcx
0x383ac8563  mov     rdx, cs:off_383B48E28; "<Sm_Shiloh::LoadDll|API|SNI> pFuncs: %p"...
0x383ac856a  lea     rcx, [r11+10h]
0x383ac856e  call    _bidScopeEnterA
0x383ac8573  lea     rax, aConnectionobje; "ConnectionObjectSize"
0x383ac857a  mov     [rsp+0A8h+lpProcName], rax
0x383ac857f  lea     rax, aConnectionopen; "ConnectionOpen"
0x383ac8586  mov     [rsp+0A8h+var_68], rax
0x383ac858b  lea     rax, aConnectionread; "ConnectionRead"
0x383ac8592  mov     [rsp+0A8h+var_60], rax
0x383ac8597  lea     rax, aConnectionwrit; "ConnectionWrite"
0x383ac859e  mov     [rsp+0A8h+var_58], rax
0x383ac85a3  lea     rax, aConnectionclos; "ConnectionClose"
0x383ac85aa  mov     [rsp+0A8h+var_50], rax
0x383ac85af  lea     rax, aConnectionchec; "ConnectionCheckForData"
0x383ac85b6  mov     [rsp+0A8h+var_48], rax
0x383ac85bb  lea     rcx, aDbmslpcnDll; "dbmslpcn.dll"
0x383ac85c2  call    SNILoadSystemLibA
0x383ac85c7  mov     cs:hModule, rax
0x383ac85ce  test    rax, rax
0x383ac85d1  jnz     short loc_383AC862B
0x383ac85d3  call    cs:__imp_GetLastError
0x383ac85d9  mov     ebx, eax
0x383ac85db  test    byte ptr cs:_bidGblFlags, 2
0x383ac85e2  jz      short loc_383AC8620
0x383ac85e4  mov     rcx, cs:off_383B48188; "<Sm_Shiloh::LoadDll|ERR|SNI> ProviderNu"...
0x383ac85eb  test    rcx, rcx
0x383ac85ee  jz      short loc_383AC8620
0x383ac85f0  mov     ecx, 0C3D8h; unsigned int
0x383ac85f5  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ac85fa  mov     [rsp+0A8h+var_80], ebx
0x383ac85fe  mov     [rsp+0A8h+var_88], eax
0x383ac8602  mov     r9d, 4
0x383ac8608  mov     r8, cs:off_383B48188; "<Sm_Shiloh::LoadDll|ERR|SNI> ProviderNu"...
0x383ac860f  mov     edx, 0CC00h
0x383ac8614  mov     rcx, cs:off_383B45B08; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac861b  call    _bidTraceA
0x383ac8620  mov     r8d, 0C3D8h
0x383ac8626  jmp     loc_383AC8765
0x383ac862b  xor     ebx, ebx
0x383ac862d  nop     dword ptr [rax]
0x383ac8630  mov     rdx, [rsp+rbx+0A8h+lpProcName]; lpProcName
0x383ac8635  mov     rcx, rax; hModule
0x383ac8638  call    cs:__imp_GetProcAddress
0x383ac863e  mov     [rsp+rbx+0A8h+var_40], rax
0x383ac8643  test    rax, rax
0x383ac8646  jz      loc_383AC8712
0x383ac864c  add     rbx, 8
0x383ac8650  cmp     rbx, 30h ; '0'
0x383ac8654  jge     short loc_383AC865F
0x383ac8656  mov     rax, cs:hModule
0x383ac865d  jmp     short loc_383AC8630
0x383ac865f  mov     rax, [rsp+0A8h+var_40]
0x383ac8664  mov     [rdi], rax
0x383ac8667  mov     rax, [rsp+0A8h+var_38]
0x383ac866c  mov     [rdi+8], rax
0x383ac8670  mov     rax, [rsp+0A8h+var_30]
0x383ac8675  mov     [rdi+10h], rax
0x383ac8679  mov     rax, [rsp+0A8h+var_28]
0x383ac8681  mov     [rdi+18h], rax
0x383ac8685  mov     rax, [rsp+0A8h+var_20]
0x383ac868d  mov     [rdi+20h], rax
0x383ac8691  mov     rax, [rsp+0A8h+var_18]
0x383ac8699  mov     [rdi+28h], rax
0x383ac869d  mov     eax, cs:_bidGblFlags
0x383ac86a3  and     eax, 20002h
0x383ac86a8  cmp     eax, 20002h
0x383ac86ad  jnz     short loc_383AC86D7
0x383ac86af  mov     rax, cs:off_383B48178; "<Sm_Shiloh::LoadDll|RET|SNI> %d{WINERR}"...
0x383ac86b6  test    rax, rax
0x383ac86b9  jz      short loc_383AC86D7
0x383ac86bb  xor     r9d, r9d
0x383ac86be  mov     r8, cs:off_383B48178; "<Sm_Shiloh::LoadDll|RET|SNI> %d{WINERR}"...
0x383ac86c5  mov     edx, 11000h
0x383ac86ca  mov     rcx, cs:off_383B45AF8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac86d1  call    _bidTraceA
0x383ac86d6  nop
0x383ac86d7  cmp     [rsp+0A8h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383ac86e0  jz      short loc_383AC870B
0x383ac86e2  test    byte ptr cs:_bidGblFlags, 4
0x383ac86e9  jz      short loc_383AC870B
0x383ac86eb  mov     rcx, cs:_bidID
0x383ac86f2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ac86f6  jz      short loc_383AC870B
0x383ac86f8  lea     r9, [rsp+0A8h+arg_8]
0x383ac8700  xor     r8d, r8d
0x383ac8703  xor     edx, edx
0x383ac8705  call    cs:off_383B15058
0x383ac870b  xor     eax, eax
0x383ac870d  jmp     loc_383AC87FE
0x383ac8712  call    cs:__imp_GetLastError
0x383ac8718  mov     ebx, eax
0x383ac871a  test    byte ptr cs:_bidGblFlags, 2
0x383ac8721  jz      short loc_383AC875F
0x383ac8723  mov     rax, cs:off_383B48180; "<Sm_Shiloh::LoadDll|ERR|SNI> ProviderNu"...
0x383ac872a  test    rax, rax
0x383ac872d  jz      short loc_383AC875F
0x383ac872f  mov     ecx, 0C3D9h; unsigned int
0x383ac8734  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x383ac8739  mov     [rsp+0A8h+var_80], ebx
0x383ac873d  mov     [rsp+0A8h+var_88], eax
0x383ac8741  mov     r9d, 4
0x383ac8747  mov     r8, cs:off_383B48180; "<Sm_Shiloh::LoadDll|ERR|SNI> ProviderNu"...
0x383ac874e  mov     edx, 0F400h
0x383ac8753  mov     rcx, cs:off_383B45B00; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac875a  call    _bidTraceA
0x383ac875f  mov     r8d, 0C3D9h
0x383ac8765  mov     edx, ebx
0x383ac8767  mov     ecx, 4
0x383ac876c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x383ac8771  mov     rcx, cs:hModule; hLibModule
0x383ac8778  test    rcx, rcx
0x383ac877b  jz      short loc_383AC8783
0x383ac877d  call    cs:__imp_FreeLibrary
0x383ac8783  mov     cs:hModule, 0
0x383ac878e  mov     eax, cs:_bidGblFlags
0x383ac8794  and     eax, 20002h
0x383ac8799  cmp     eax, 20002h
0x383ac879e  jnz     short loc_383AC87C8
0x383ac87a0  mov     rax, cs:off_383B48170; "<Sm_Shiloh::LoadDll|RET|SNI> %d{WINERR}"...
0x383ac87a7  test    rax, rax
0x383ac87aa  jz      short loc_383AC87C8
0x383ac87ac  mov     r9d, ebx
0x383ac87af  mov     r8, cs:off_383B48170; "<Sm_Shiloh::LoadDll|RET|SNI> %d{WINERR}"...
0x383ac87b6  mov     edx, 13800h
0x383ac87bb  mov     rcx, cs:off_383B45AF0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ac87c2  call    _bidTraceA
0x383ac87c7  nop
0x383ac87c8  cmp     [rsp+0A8h+arg_8], 0FFFFFFFFFFFFFFFFh
0x383ac87d1  jz      short loc_383AC87FC
0x383ac87d3  test    byte ptr cs:_bidGblFlags, 4
0x383ac87da  jz      short loc_383AC87FC
0x383ac87dc  mov     rcx, cs:_bidID
0x383ac87e3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ac87e7  jz      short loc_383AC87FC
0x383ac87e9  lea     r9, [rsp+0A8h+arg_8]
0x383ac87f1  xor     r8d, r8d
0x383ac87f4  xor     edx, edx
0x383ac87f6  call    cs:off_383B15058
0x383ac87fc  mov     eax, ebx
0x383ac87fe  mov     rbx, [rsp+0A8h+arg_0]
0x383ac8806  add     rsp, 0A0h
0x383ac880d  pop     rdi
0x383ac880e  retn
```
