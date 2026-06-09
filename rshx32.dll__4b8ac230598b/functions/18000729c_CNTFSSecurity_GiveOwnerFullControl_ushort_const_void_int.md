# CNTFSSecurity::GiveOwnerFullControl(ushort const *,void *,int *)

- ea: `0x18000729c`
- end: `0x180007381`
- name: `?GiveOwnerFullControl@CNTFSSecurity@@QEAAJPEBGPEAXPEAH@Z`
- size: `229`
- prototype: `__int64 __fastcall(HWND *this, const unsigned __int16 *, void *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007780`

## callees

- `0x180006398`
- `0x18000729c`
- `0x180019404`
- `0x18001d370`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000731e`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000731e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000734b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18000734b`

## pseudocode

```c
__int64 __fastcall CNTFSSecurity::GiveOwnerFullControl(HWND *this, const unsigned __int16 *a2, void *a3, int *a4)
{
  __int64 result; // rax
  HWND v9; // r8
  _OWORD FileInformation[2]; // [rsp+30h] [rbp-58h] BYREF
  int v11; // [rsp+50h] [rbp-38h]

  if ( !this[43] )
  {
    if ( (unsigned int)MsgPopup(this[41], 0xBu, 0x57u, 0x10034u, g_hInstance, (char)a2) != 6 )
      return 1;
    result = CNTFSSecurity::BuildOwnerFullControlSD((CNTFSSecurity *)this, a3);
    if ( (int)result < 0 )
      return result;
  }
  v9 = this[43];
  if ( !v9 || !SetFileSecurityW(a2, 4u, v9) )
    return 1;
  *a4 = 1;
  v11 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( GetFileAttributesExW(a2, GetFileExInfoStandard, FileInformation) )
  {
    if ( (FileInformation[0] & 0x10) != 0 )
      *a4 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000729c  push    rbx
0x18000729e  push    rbp
0x18000729f  push    rsi
0x1800072a0  push    rdi
0x1800072a1  sub     rsp, 68h
0x1800072a5  mov     rax, cs:__security_cookie
0x1800072ac  xor     rax, rsp
0x1800072af  mov     [rsp+88h+var_30], rax
0x1800072b4  cmp     qword ptr [rcx+158h], 0
0x1800072bc  mov     rsi, r9
0x1800072bf  mov     rbp, r8
0x1800072c2  mov     rdi, rdx
0x1800072c5  mov     rbx, rcx
0x1800072c8  jnz     short loc_18000730A
0x1800072ca  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800072d1  mov     r9d, 10034h; uType
0x1800072d7  mov     rcx, [rcx+148h]; hWnd
0x1800072de  mov     qword ptr [rsp+88h+var_60], rdx; char
0x1800072e3  mov     edx, 0Bh; unsigned int
0x1800072e8  mov     [rsp+88h+hAppInst], rax; hAppInst
0x1800072ed  lea     r8d, [rdx+4Ch]; unsigned int
0x1800072f1  call    MsgPopup
0x1800072f6  cmp     eax, 6
0x1800072f9  jnz     short loc_180007366
0x1800072fb  mov     rdx, rbp; void *
0x1800072fe  mov     rcx, rbx; this
0x180007301  call    ?BuildOwnerFullControlSD@CNTFSSecurity@@IEAAJPEAX@Z; CNTFSSecurity::BuildOwnerFullControlSD(void *)
0x180007306  test    eax, eax
0x180007308  js      short loc_18000736B
0x18000730a  mov     r8, [rbx+158h]; pSecurityDescriptor
0x180007311  test    r8, r8
0x180007314  jz      short loc_180007366
0x180007316  mov     edx, 4; SecurityInformation
0x18000731b  mov     rcx, rdi; lpFileName
0x18000731e  call    cs:__imp_SetFileSecurityW
0x180007324  test    eax, eax
0x180007326  jz      short loc_180007366
0x180007328  xorps   xmm0, xmm0
0x18000732b  mov     dword ptr [rsi], 1
0x180007331  xor     eax, eax
0x180007333  lea     r8, [rsp+88h+FileInformation]; lpFileInformation
0x180007338  xor     edx, edx; fInfoLevelId
0x18000733a  mov     [rsp+88h+var_38], eax
0x18000733e  mov     rcx, rdi; lpFileName
0x180007341  movups  [rsp+88h+FileInformation], xmm0
0x180007346  movups  [rsp+88h+var_48], xmm0
0x18000734b  call    cs:__imp_GetFileAttributesExW
0x180007351  test    eax, eax
0x180007353  jz      short loc_180007362
0x180007355  test    byte ptr [rsp+88h+FileInformation], 10h
0x18000735a  jz      short loc_180007362
0x18000735c  mov     dword ptr [rsi], 0
0x180007362  xor     eax, eax
0x180007364  jmp     short loc_18000736B
0x180007366  mov     eax, 1
0x18000736b  mov     rcx, [rsp+88h+var_30]
0x180007370  xor     rcx, rsp; StackCookie
0x180007373  call    __security_check_cookie
0x180007378  add     rsp, 68h
0x18000737c  pop     rdi
0x18000737d  pop     rsi
0x18000737e  pop     rbp
0x18000737f  pop     rbx
0x180007380  retn
```
