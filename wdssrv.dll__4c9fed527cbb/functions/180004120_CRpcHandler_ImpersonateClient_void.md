# CRpcHandler::ImpersonateClient(void *)

- ea: `0x180004120`
- end: `0x1800042e1`
- name: `?ImpersonateClient@CRpcHandler@@UEAAKPEAX@Z`
- size: `449`
- prototype: `unsigned int __fastcall(CRpcHandler *__hidden this, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003944`
- `0x180004120`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18000416b`
- `RPCRT4!RpcImpersonateClient` at `0x18000416b`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800042b1`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x1800042b1`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004298`
- `WdsServerCommonLib!?Trace@CTrace@@QEAAXKPEBGZZ` at `0x180004298`
- `WdsServerCommonLib!?GetCurrentUser@@YAKPEAPEAGPEBG@Z` at `0x1800041b0`
- `WdsServerCommonLib!?GetCurrentUser@@YAKPEAPEAGPEBG@Z` at `0x1800041b0`

## string_xrefs

- `0x180004267`: `[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}] Client=%s Impersonation=%s`

## pseudocode

```c
__int64 __fastcall CRpcHandler::ImpersonateClient(CRpcHandler *this, RPC_BINDING_HANDLE *a2)
{
  unsigned int CurrentUser; // edi
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  const wchar_t *v8; // r9
  unsigned __int16 *v10; // [rsp+C8h] [rbp+10h] BYREF

  v10 = 0;
  if ( a2 )
  {
    if ( ((_BYTE)a2[14] & 1) != 0 )
    {
      v5 = RpcImpersonateClient(a2[8]);
      CurrentUser = ElValidateWin32(v5, v6, "base\\eco\\wds\\wdssrv\\server\\src\\rpchandler.cpp", 1534);
      if ( !CurrentUser )
      {
        if ( *((_DWORD *)this + 40) )
        {
          CurrentUser = GetCurrentUser(&v10, L"<Failed>");
          if ( !CurrentUser )
          {
            v7 = *((_QWORD *)a2[280] + 8);
            if ( v7 )
              v8 = *(const wchar_t **)(v7 + 16);
            else
              v8 = L"<Unknown>";
            CTrace::Trace(
              (CTrace *)qword_180039310,
              0x10000u,
              L"[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}] Client=%s Impersonation=%s",
              v8,
              *((_DWORD *)a2 + 292),
              *((unsigned __int16 *)a2 + 586),
              *((unsigned __int16 *)a2 + 587),
              *((unsigned __int8 *)a2 + 1176),
              *((unsigned __int8 *)a2 + 1177),
              *((unsigned __int8 *)a2 + 1178),
              *((unsigned __int8 *)a2 + 1179),
              *((unsigned __int8 *)a2 + 1180),
              *((unsigned __int8 *)a2 + 1181),
              *((unsigned __int8 *)a2 + 1182),
              *((unsigned __int8 *)a2 + 1183),
              (char *)a2 + 132,
              v10);
          }
        }
      }
      if ( v10 )
        WdsPrivateHpFree(v10);
    }
    else
    {
      return 1244;
    }
  }
  else
  {
    return 87;
  }
  return CurrentUser;
}

```

## disassembly

```asm
0x180004120  mov     rax, rsp
0x180004123  mov     [rax+8], rbx
0x180004127  mov     [rax+18h], rbp
0x18000412b  mov     [rax+20h], rsi
0x18000412f  push    rdi
0x180004130  push    r12
0x180004132  push    r13
0x180004134  push    r14
0x180004136  push    r15
0x180004138  sub     rsp, 90h
0x18000413f  and     qword ptr [rax+10h], 0
0x180004144  mov     rbx, rdx
0x180004147  mov     rsi, rcx
0x18000414a  test    rdx, rdx
0x18000414d  jnz     short loc_180004157
0x18000414f  lea     edi, [rdx+57h]
0x180004152  jmp     loc_1800042BD
0x180004157  test    byte ptr [rdx+70h], 1
0x18000415b  jnz     short loc_180004167
0x18000415d  mov     edi, 4DCh
0x180004162  jmp     loc_1800042BD
0x180004167  mov     rcx, [rdx+40h]; BindingHandle
0x18000416b  call    cs:__imp_RpcImpersonateClient
0x180004172  nop     dword ptr [rax+rax+00h]
0x180004177  mov     r9d, 5FEh
0x18000417d  lea     r8, aBaseEcoWdsWdss_6; "base\\eco\\wds\\wdssrv\\server\\src\\rp"...
0x180004184  mov     ecx, eax
0x180004186  call    ElValidateWin32
0x18000418b  mov     edi, eax
0x18000418d  test    eax, eax
0x18000418f  jnz     loc_1800042A4
0x180004195  cmp     [rsi+0A0h], eax
0x18000419b  jz      loc_1800042A4
0x1800041a1  lea     rdx, aFailed; "<Failed>"
0x1800041a8  lea     rcx, [rsp+0B8h+arg_8]
0x1800041b0  call    cs:__imp_?GetCurrentUser@@YAKPEAPEAGPEBG@Z; GetCurrentUser(ushort * *,ushort const *)
0x1800041b7  nop     dword ptr [rax+rax+00h]
0x1800041bc  mov     edi, eax
0x1800041be  test    eax, eax
0x1800041c0  jnz     loc_1800042A4
0x1800041c6  mov     rax, [rbx+8C0h]
0x1800041cd  movzx   edx, byte ptr [rbx+49Fh]
0x1800041d4  movzx   r8d, byte ptr [rbx+49Eh]
0x1800041dc  movzx   r10d, byte ptr [rbx+49Dh]
0x1800041e4  mov     rcx, [rax+40h]
0x1800041e8  movzx   r11d, byte ptr [rbx+49Ch]
0x1800041f0  movzx   esi, byte ptr [rbx+49Bh]
0x1800041f7  movzx   ebp, byte ptr [rbx+49Ah]
0x1800041fe  movzx   r14d, byte ptr [rbx+499h]
0x180004206  movzx   r15d, byte ptr [rbx+498h]
0x18000420e  movzx   r12d, word ptr [rbx+496h]
0x180004216  movzx   r13d, word ptr [rbx+494h]
0x18000421e  test    rcx, rcx
0x180004221  jz      short loc_180004229
0x180004223  mov     r9, [rcx+10h]
0x180004227  jmp     short loc_180004230
0x180004229  lea     r9, aUnknown_0; "<Unknown>"
0x180004230  mov     rax, [rsp+0B8h+arg_8]
0x180004238  lea     rcx, [rbx+84h]
0x18000423f  mov     [rsp+0B8h+var_38], rax
0x180004247  mov     eax, [rbx+490h]
0x18000424d  mov     [rsp+0B8h+var_40], rcx
0x180004252  lea     rcx, qword_180039310
0x180004259  mov     [rsp+0B8h+var_48], edx
0x18000425d  mov     edx, 10000h
0x180004262  mov     [rsp+0B8h+var_50], r8d
0x180004267  lea     r8, aSRpcEp08x04x04_1; "[%s][RPC][Ep:{%08X-%04X-%04X-%02X%02X-%"...
0x18000426e  mov     [rsp+0B8h+var_58], r10d
0x180004273  mov     [rsp+0B8h+var_60], r11d
0x180004278  mov     [rsp+0B8h+var_68], esi
0x18000427c  mov     [rsp+0B8h+var_70], ebp
0x180004280  mov     [rsp+0B8h+var_78], r14d
0x180004285  mov     [rsp+0B8h+var_80], r15d
0x18000428a  mov     [rsp+0B8h+var_88], r12d
0x18000428f  mov     [rsp+0B8h+var_90], r13d
0x180004294  mov     [rsp+0B8h+var_98], eax
0x180004298  call    cs:__imp_?Trace@CTrace@@QEAAXKPEBGZZ; CTrace::Trace(ulong,ushort const *,...)
0x18000429f  nop     dword ptr [rax+rax+00h]
0x1800042a4  mov     rcx, [rsp+0B8h+arg_8]
0x1800042ac  test    rcx, rcx
0x1800042af  jz      short loc_1800042BD
0x1800042b1  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x1800042b8  nop     dword ptr [rax+rax+00h]
0x1800042bd  lea     r11, [rsp+0B8h+var_28]
0x1800042c5  mov     eax, edi
0x1800042c7  mov     rbx, [r11+30h]
0x1800042cb  mov     rbp, [r11+40h]
0x1800042cf  mov     rsi, [r11+48h]
0x1800042d3  mov     rsp, r11
0x1800042d6  pop     r15
0x1800042d8  pop     r14
0x1800042da  pop     r13
0x1800042dc  pop     r12
0x1800042de  pop     rdi
0x1800042df  retn
```
