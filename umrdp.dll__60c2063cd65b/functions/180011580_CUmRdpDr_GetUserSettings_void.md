# CUmRdpDr::GetUserSettings(void)

- ea: `0x180011580`
- end: `0x18001164e`
- name: `?GetUserSettings@CUmRdpDr@@AEAAXXZ`
- size: `206`
- prototype: `void __fastcall(CUmRdpDr *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011850`

## callees

- `0x180011580`
- `0x180047ebe`
- `0x180047ef0`

## import_xrefs

- `WINSTA!WinStationQueryInformationW` at `0x1800115f9`
- `WINSTA!WinStationQueryInformationW` at `0x1800115f9`
- `WINSTA!WinStationOpenServerW` at `0x1800115c9`
- `WINSTA!WinStationOpenServerW` at `0x1800115c9`
- `WINSTA!WinStationCloseServer` at `0x180011627`
- `WINSTA!WinStationCloseServer` at `0x180011627`

## pseudocode

```c
void __fastcall CUmRdpDr::GetUserSettings(CUmRdpDr *this)
{
  __int64 v2; // rdi
  int v3; // ecx
  _DWORD v4[4]; // [rsp+30h] [rbp-A98h] BYREF
  _BYTE v5[124]; // [rsp+40h] [rbp-A88h] BYREF
  unsigned int v6; // [rsp+BCh] [rbp-A0Ch]

  memset_0(v5, 0, 0xA68u);
  v4[0] = 0;
  *(_QWORD *)((char *)this + 1972) = 0;
  v2 = WinStationOpenServerW(0);
  if ( v2 )
  {
    if ( (unsigned __int8)WinStationQueryInformationW(v2, *(unsigned int *)this, 1, v5, 2664, v4) )
    {
      v3 = (v6 >> 19) & 1;
      *((_DWORD *)this + 493) = (v6 >> 18) & 1;
      *((_DWORD *)this + 494) = v3;
    }
    WinStationCloseServer(v2);
  }
}

```

## disassembly

```asm
0x180011580  mov     [rsp+arg_8], rbx
0x180011585  push    rdi
0x180011586  sub     rsp, 0AC0h
0x18001158d  mov     rax, cs:__security_cookie
0x180011594  xor     rax, rsp
0x180011597  mov     [rsp+0AC8h+var_18], rax
0x18001159f  mov     rbx, rcx
0x1800115a2  xor     edx, edx; Val
0x1800115a4  lea     rcx, [rsp+0AC8h+var_A88]; void *
0x1800115a9  mov     r8d, 0A68h; Size
0x1800115af  call    memset_0
0x1800115b4  xor     ecx, ecx
0x1800115b6  mov     [rsp+0AC8h+var_A98], 0
0x1800115be  mov     qword ptr [rbx+7B4h], 0
0x1800115c9  call    cs:__imp_WinStationOpenServerW
0x1800115cf  mov     rdi, rax
0x1800115d2  test    rax, rax
0x1800115d5  jz      short loc_18001162D
0x1800115d7  mov     edx, [rbx]
0x1800115d9  lea     rax, [rsp+0AC8h+var_A98]
0x1800115de  mov     [rsp+0AC8h+var_AA0], rax
0x1800115e3  lea     r9, [rsp+0AC8h+var_A88]
0x1800115e8  mov     r8d, 1
0x1800115ee  mov     [rsp+0AC8h+var_AA8], 0A68h
0x1800115f6  mov     rcx, rdi
0x1800115f9  call    cs:__imp_WinStationQueryInformationW
0x1800115ff  test    al, al
0x180011601  jz      short loc_180011624
0x180011603  mov     ecx, [rsp+0AC8h+var_A0C]
0x18001160a  mov     eax, ecx
0x18001160c  shr     eax, 12h
0x18001160f  and     eax, 1
0x180011612  shr     ecx, 13h
0x180011615  and     ecx, 1
0x180011618  mov     [rbx+7B4h], eax
0x18001161e  mov     [rbx+7B8h], ecx
0x180011624  mov     rcx, rdi
0x180011627  call    cs:__imp_WinStationCloseServer
0x18001162d  mov     rcx, [rsp+0AC8h+var_18]
0x180011635  xor     rcx, rsp; StackCookie
0x180011638  call    __security_check_cookie
0x18001163d  mov     rbx, [rsp+0AC8h+arg_8]
0x180011645  add     rsp, 0AC0h
0x18001164c  pop     rdi
0x18001164d  retn
```
