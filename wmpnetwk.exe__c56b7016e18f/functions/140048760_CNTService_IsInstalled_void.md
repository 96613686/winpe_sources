# CNTService::IsInstalled(void)

- ea: `0x140048760`
- end: `0x1400488ee`
- name: `?IsInstalled@CNTService@@QEAAHXZ`
- size: `398`
- prototype: `__int64 __fastcall(CNTService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x1400448e0`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x140048760`

## import_xrefs

- `ADVAPI32!OpenSCManagerW` at `0x1400487ac`
- `ADVAPI32!OpenSCManagerW` at `0x1400487ac`
- `ADVAPI32!OpenServiceW` at `0x1400487f2`
- `ADVAPI32!OpenServiceW` at `0x1400487f2`
- `ADVAPI32!CloseServiceHandle` at `0x14004882f`
- `ADVAPI32!CloseServiceHandle` at `0x140048873`
- `ADVAPI32!CloseServiceHandle` at `0x14004882f`
- `ADVAPI32!CloseServiceHandle` at `0x140048873`
- `KERNEL32!GetLastError` at `0x14004884f`
- `KERNEL32!GetLastError` at `0x140048893`
- `KERNEL32!GetLastError` at `0x14004884f`
- `KERNEL32!GetLastError` at `0x140048893`

## pseudocode

```c
__int64 __fastcall CNTService::IsInstalled(LPCWSTR *this)
{
  unsigned int v2; // edi
  SC_HANDLE v3; // rbp
  SC_HANDLE v4; // rsi
  DWORD LastError; // eax
  PVOID *v6; // rcx
  DWORD v7; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  v2 = 0;
  v3 = OpenSCManagerW(0, 0, 0xF003Fu);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
    }
    v4 = OpenServiceW(v3, this[5], 1u);
    if ( v4 )
    {
      v2 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
      }
      CloseServiceHandle(v4);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, LastError);
    }
    CloseServiceHandle(v3);
    goto LABEL_24;
  }
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v7);
LABEL_24:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 5u )
    WPP_SF_d(v6[2], 27, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x140048760  push    rbp
0x140048762  push    rsi
0x140048763  push    rdi
0x140048764  push    r14
0x140048766  push    r15
0x140048768  sub     rsp, 20h
0x14004876c  mov     rsi, rcx
0x14004876f  mov     rcx, cs:WPP_GLOBAL_Control
0x140048776  lea     r14, WPP_GLOBAL_Control
0x14004877d  lea     r15, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x140048784  cmp     rcx, r14
0x140048787  jz      short loc_1400487A0
0x140048789  test    byte ptr [rcx+1Ch], 1
0x14004878d  jz      short loc_1400487A0
0x14004878f  mov     rcx, [rcx+10h]
0x140048793  mov     edx, 16h
0x140048798  mov     r8, r15
0x14004879b  call    WPP_SF_
0x1400487a0  xor     edx, edx; lpDatabaseName
0x1400487a2  xor     ecx, ecx; lpMachineName
0x1400487a4  mov     r8d, 0F003Fh; dwDesiredAccess
0x1400487aa  xor     edi, edi
0x1400487ac  call    cs:__imp_OpenSCManagerW
0x1400487b2  mov     rbp, rax
0x1400487b5  test    rax, rax
0x1400487b8  jz      loc_14004887B
0x1400487be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400487c5  cmp     rcx, r14
0x1400487c8  jz      short loc_1400487E5
0x1400487ca  test    byte ptr [rcx+1Ch], 2
0x1400487ce  jz      short loc_1400487E5
0x1400487d0  cmp     byte ptr [rcx+19h], 4
0x1400487d4  jb      short loc_1400487E5
0x1400487d6  mov     rcx, [rcx+10h]
0x1400487da  lea     edx, [rdi+17h]
0x1400487dd  mov     r8, r15
0x1400487e0  call    WPP_SF_
0x1400487e5  mov     rdx, [rsi+28h]; lpServiceName
0x1400487e9  mov     r8d, 1; dwDesiredAccess
0x1400487ef  mov     rcx, rbp; hSCManager
0x1400487f2  call    cs:__imp_OpenServiceW
0x1400487f8  mov     rsi, rax
0x1400487fb  test    rax, rax
0x1400487fe  jz      short loc_140048837
0x140048800  mov     edi, 1
0x140048805  mov     rcx, cs:WPP_GLOBAL_Control
0x14004880c  cmp     rcx, r14
0x14004880f  jz      short loc_14004882C
0x140048811  test    byte ptr [rcx+1Ch], 2
0x140048815  jz      short loc_14004882C
0x140048817  cmp     byte ptr [rcx+19h], 4
0x14004881b  jb      short loc_14004882C
0x14004881d  mov     rcx, [rcx+10h]
0x140048821  lea     edx, [rdi+17h]
0x140048824  mov     r8, r15
0x140048827  call    WPP_SF_
0x14004882c  mov     rcx, rsi; hSCObject
0x14004882f  call    cs:__imp_CloseServiceHandle
0x140048835  jmp     short loc_140048870
0x140048837  mov     rax, cs:WPP_GLOBAL_Control
0x14004883e  cmp     rax, r14
0x140048841  jz      short loc_140048870
0x140048843  test    byte ptr [rax+1Ch], 2
0x140048847  jz      short loc_140048870
0x140048849  cmp     byte ptr [rax+19h], 2
0x14004884d  jb      short loc_140048870
0x14004884f  call    cs:__imp_GetLastError
0x140048855  mov     rcx, cs:WPP_GLOBAL_Control
0x14004885c  mov     edx, 19h
0x140048861  mov     r9d, eax
0x140048864  mov     r8, r15
0x140048867  mov     rcx, [rcx+10h]
0x14004886b  call    WPP_SF_d
0x140048870  mov     rcx, rbp; hSCObject
0x140048873  call    cs:__imp_CloseServiceHandle
0x140048879  jmp     short loc_1400488B4
0x14004887b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048882  cmp     rcx, r14
0x140048885  jz      short loc_1400488E0
0x140048887  test    byte ptr [rcx+1Ch], 2
0x14004888b  jz      short loc_1400488BB
0x14004888d  cmp     byte ptr [rcx+19h], 2
0x140048891  jb      short loc_1400488BB
0x140048893  call    cs:__imp_GetLastError
0x140048899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400488a0  mov     edx, 1Ah
0x1400488a5  mov     r9d, eax
0x1400488a8  mov     r8, r15
0x1400488ab  mov     rcx, [rcx+10h]
0x1400488af  call    WPP_SF_d
0x1400488b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400488bb  cmp     rcx, r14
0x1400488be  jz      short loc_1400488E0
0x1400488c0  test    byte ptr [rcx+1Ch], 1
0x1400488c4  jz      short loc_1400488E0
0x1400488c6  cmp     byte ptr [rcx+19h], 5
0x1400488ca  jb      short loc_1400488E0
0x1400488cc  mov     rcx, [rcx+10h]
0x1400488d0  mov     edx, 1Bh
0x1400488d5  mov     r9d, edi
0x1400488d8  mov     r8, r15
0x1400488db  call    WPP_SF_d
0x1400488e0  mov     eax, edi
0x1400488e2  add     rsp, 20h
0x1400488e6  pop     r15
0x1400488e8  pop     r14
0x1400488ea  pop     rdi
0x1400488eb  pop     rsi
0x1400488ec  pop     rbp
0x1400488ed  retn
```
