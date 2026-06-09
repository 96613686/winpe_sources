# CNTFSSecurity::SetSecurity(ulong,void *)

- ea: `0x180007950`
- end: `0x180007a50`
- name: `?SetSecurity@CNTFSSecurity@@UEAAJKPEAX@Z`
- size: `256`
- prototype: `int __fastcall(CNTFSSecurity *this, unsigned int, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006ce8`
- `0x180007950`
- `0x180007a58`
- `0x18000c740`
- `0x180015f8c`
- `0x18001606c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180007979`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180007979`
- `USER32!GetLastActivePopup` at `0x1800079a9`
- `USER32!GetLastActivePopup` at `0x1800079c8`
- `USER32!GetLastActivePopup` at `0x1800079a9`
- `USER32!GetLastActivePopup` at `0x1800079c8`

## pseudocode

```c
int __fastcall CNTFSSecurity::SetSecurity(CNTFSSecurity *this, unsigned int a2, void *a3)
{
  CNTFSSecurity *v7; // rcx
  HWND LastActivePopup; // rax
  HWND hWnd; // rax
  int v10; // r9d

  if ( !a3 )
    return -2147467261;
  if ( !IsValidSecurityDescriptor(a3) )
    return -2147024809;
  if ( (a2 & 4) != 0 )
    CNTFSSecurity::FixSynchronizeAccess(v7, a2, a3);
  if ( *((_DWORD *)this + 96) )
  {
    LastActivePopup = GetLastActivePopup(*((HWND *)this + 11));
    if ( !(unsigned int)SetAclOnRemoteNetworkDrive(*((unsigned __int16 **)this + 7), a2, a3, LastActivePopup) )
      return 1;
  }
  hWnd = GetLastActivePopup(*((HWND *)this + 11));
  if ( !SetAclOnSystemPaths(
          *((PCNZWCH *)this + 7),
          *((PCNZWCH *)this + 44),
          *((PCNZWCH *)this + 45),
          *((PCNZWCH *)this + 46),
          a2,
          hWnd) )
    return 1;
  if ( (a2 & 0xC100) != 0 )
  {
    a2 &= 0xFFFF3EFF;
    v10 = 1;
    return CNTFSSecurity::SetSecurityLocal(this, a2, a3, v10);
  }
  if ( (*((_BYTE *)this + 64) & 4) != 0 && a2 != 1 )
  {
    v10 = 0;
    return CNTFSSecurity::SetSecurityLocal(this, a2, a3, v10);
  }
  return CSecurityInformation::SetSecurity(this, a2, a3);
}

```

## disassembly

```asm
0x180007950  mov     [rsp+arg_0], rbx
0x180007955  mov     [rsp+arg_8], rsi
0x18000795a  push    rdi
0x18000795b  sub     rsp, 30h
0x18000795f  mov     rsi, r8
0x180007962  mov     ebx, edx
0x180007964  mov     rdi, rcx
0x180007967  test    r8, r8
0x18000796a  jnz     short loc_180007976
0x18000796c  mov     eax, 80004003h
0x180007971  jmp     loc_180007A40
0x180007976  mov     rcx, rsi; pSecurityDescriptor
0x180007979  call    cs:__imp_IsValidSecurityDescriptor
0x18000797f  test    eax, eax
0x180007981  jnz     short loc_18000798D
0x180007983  mov     eax, 80070057h
0x180007988  jmp     loc_180007A40
0x18000798d  test    bl, 4
0x180007990  jz      short loc_18000799C
0x180007992  mov     r8, rsi; void *
0x180007995  mov     edx, ebx; unsigned int
0x180007997  call    ?FixSynchronizeAccess@CNTFSSecurity@@IEAAXKPEAX@Z; CNTFSSecurity::FixSynchronizeAccess(ulong,void *)
0x18000799c  cmp     dword ptr [rdi+180h], 0
0x1800079a3  jz      short loc_1800079C4
0x1800079a5  mov     rcx, [rdi+58h]; hWnd
0x1800079a9  call    cs:__imp_GetLastActivePopup
0x1800079af  mov     rcx, [rdi+38h]; unsigned __int16 *
0x1800079b3  mov     r8, rsi; void *
0x1800079b6  mov     r9, rax; HWND
0x1800079b9  mov     edx, ebx; unsigned int
0x1800079bb  call    ?SetAclOnRemoteNetworkDrive@@YAHPEAGKPEAXPEAUHWND__@@@Z; SetAclOnRemoteNetworkDrive(ushort *,ulong,void *,HWND__ *)
0x1800079c0  test    eax, eax
0x1800079c2  jz      short loc_1800079F9
0x1800079c4  mov     rcx, [rdi+58h]; hWnd
0x1800079c8  call    cs:__imp_GetLastActivePopup
0x1800079ce  mov     r9, [rdi+170h]; PCNZWCH
0x1800079d5  mov     r8, [rdi+168h]; PCNZWCH
0x1800079dc  mov     rdx, [rdi+160h]; lpString1
0x1800079e3  mov     rcx, [rdi+38h]; lpString2
0x1800079e7  mov     [rsp+38h+hWnd], rax; hWnd
0x1800079ec  mov     dword ptr [rsp+38h+var_18], ebx; char
0x1800079f0  call    ?SetAclOnSystemPaths@@YAHPEAGPEBG11KPEAUHWND__@@@Z; SetAclOnSystemPaths(ushort *,ushort const *,ushort const *,ushort const *,ulong,HWND__ *)
0x1800079f5  test    eax, eax
0x1800079f7  jnz     short loc_180007A00
0x1800079f9  mov     eax, 1
0x1800079fe  jmp     short loc_180007A40
0x180007a00  test    ebx, 0C100h
0x180007a06  jz      short loc_180007A16
0x180007a08  and     ebx, 0FFFF3EFFh
0x180007a0e  mov     r9d, 1
0x180007a14  jmp     short loc_180007A24
0x180007a16  test    byte ptr [rdi+40h], 4
0x180007a1a  jz      short loc_180007A33
0x180007a1c  cmp     ebx, 1
0x180007a1f  jz      short loc_180007A33
0x180007a21  xor     r9d, r9d; int
0x180007a24  mov     r8, rsi; void *
0x180007a27  mov     edx, ebx; unsigned int
0x180007a29  mov     rcx, rdi; this
0x180007a2c  call    ?SetSecurityLocal@CNTFSSecurity@@IEAAJKPEAXH@Z; CNTFSSecurity::SetSecurityLocal(ulong,void *,int)
0x180007a31  jmp     short loc_180007A40
0x180007a33  mov     r8, rsi; void *
0x180007a36  mov     edx, ebx; unsigned int
0x180007a38  mov     rcx, rdi; this
0x180007a3b  call    ?SetSecurity@CSecurityInformation@@UEAAJKPEAX@Z; CSecurityInformation::SetSecurity(ulong,void *)
0x180007a40  mov     rbx, [rsp+38h+arg_0]
0x180007a45  mov     rsi, [rsp+38h+arg_8]
0x180007a4a  add     rsp, 30h
0x180007a4e  pop     rdi
0x180007a4f  retn
```
