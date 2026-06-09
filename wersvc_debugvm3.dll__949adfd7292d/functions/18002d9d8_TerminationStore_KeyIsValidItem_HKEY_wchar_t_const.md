# TerminationStore::KeyIsValidItem(HKEY__ *,wchar_t const *)

- ea: `0x18002d9d8`
- end: `0x18002dad1`
- name: `?KeyIsValidItem@TerminationStore@@AEAA_NPEAUHKEY__@@PEB_W@Z`
- size: `249`
- prototype: `bool(TerminationStore *__hidden this, HKEY, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002cd78`
- `0x18002d1f0`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x1800133dc`
- `0x180013548`
- `0x18002d084`
- `0x18002d9d8`
- `0x18002dad8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002da7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002da7d`

## string_xrefs

- `0x18002da1e`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`

## pseudocode

```c
char __fastcall TerminationStore::KeyIsValidItem(TerminationStore *this, wchar_t *a2, const wchar_t *a3, __int64 a4)
{
  unsigned __int64 QWORD; // rbx
  int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  TerminationStore *v11; // rcx
  bool *v12; // [rsp+20h] [rbp-C8h]
  unsigned int v13; // [rsp+20h] [rbp-C8h]
  DWORD v14; // [rsp+28h] [rbp-C0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v16[144]; // [rsp+40h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  QWORD = UtilRegGetQWORD((HKEY)a2, a2, a3, a4, v12, v14);
  if ( !QWORD )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x148,
           (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
           (const char *)0xD,
           v13);
    if ( v7 < 0 )
    {
      v9 = 266;
LABEL_4:
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)v7, v13);
      return 0;
    }
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( QWORD > *(_QWORD *)&SystemTimeAsFileTime || *(_QWORD *)&SystemTimeAsFileTime - QWORD > 0xB2D05E00 )
    return 0;
  memset_0(v16, 0, 0x88u);
  v7 = TerminationStore::ConvertKeyToItem(v11, (HKEY)a2, a3, (struct TerminationItem *)v16);
  if ( v7 < 0 )
  {
    v9 = 297;
    goto LABEL_4;
  }
  return 1;
}

```

## disassembly

```asm
0x18002d9d8  mov     [rsp+arg_0], rbx
0x18002d9dd  mov     [rsp+arg_18], rsi
0x18002d9e2  push    rdi
0x18002d9e3  sub     rsp, 0E0h
0x18002d9ea  mov     rax, cs:__security_cookie
0x18002d9f1  xor     rax, rsp
0x18002d9f4  mov     [rsp+0E8h+var_18], rax
0x18002d9fc  mov     rcx, rdx; hKey
0x18002d9ff  mov     rsi, r8
0x18002da02  mov     rdi, rdx
0x18002da05  call    ?UtilRegGetQWORD@@YA_KPEAUHKEY__@@PEB_W1_KPEA_N_N@Z; UtilRegGetQWORD(HKEY__ *,wchar_t const *,wchar_t const *,unsigned __int64,bool *,bool)
0x18002da0a  mov     rbx, rax
0x18002da0d  test    rax, rax
0x18002da10  jnz     short loc_18002DA6F
0x18002da12  mov     rcx, [rsp+0E8h]; this
0x18002da1a  lea     r9d, [rax+0Dh]; char *
0x18002da1e  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002da25  mov     edx, 148h; void *
0x18002da2a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002da2f  test    eax, eax
0x18002da31  jns     short loc_18002DA6F
0x18002da33  mov     edx, 10Ah; void *
0x18002da38  mov     rcx, [rsp+0E8h]; this
0x18002da40  mov     r9d, eax; char *
0x18002da43  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002da48  xor     al, al
0x18002da4a  mov     rcx, [rsp+0E8h+var_18]
0x18002da52  xor     rcx, rsp; StackCookie
0x18002da55  call    __security_check_cookie
0x18002da5a  lea     r11, [rsp+0E8h+var_8]
0x18002da62  mov     rbx, [r11+10h]
0x18002da66  mov     rsi, [r11+28h]
0x18002da6a  mov     rsp, r11
0x18002da6d  pop     rdi
0x18002da6e  retn
0x18002da6f  lea     rcx, [rsp+0E8h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002da74  mov     qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002da7d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002da83  mov     rax, qword ptr [rsp+0E8h+SystemTimeAsFileTime.dwLowDateTime]
0x18002da88  cmp     rbx, rax
0x18002da8b  ja      short loc_18002DA48
0x18002da8d  sub     rax, rbx
0x18002da90  mov     ecx, 0B2D05E00h
0x18002da95  cmp     rax, rcx
0x18002da98  ja      short loc_18002DA48
0x18002da9a  xor     edx, edx; Val
0x18002da9c  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18002daa1  mov     r8d, 88h; Size
0x18002daa7  call    memset_0
0x18002daac  lea     r9, [rsp+0E8h+var_A8]; struct TerminationItem *
0x18002dab1  mov     r8, rsi; wchar_t *
0x18002dab4  mov     rdx, rdi; HKEY
0x18002dab7  call    ?ConvertKeyToItem@TerminationStore@@AEAAJPEAUHKEY__@@PEB_WPEAUTerminationItem@@@Z; TerminationStore::ConvertKeyToItem(HKEY__ *,wchar_t const *,TerminationItem *)
0x18002dabc  test    eax, eax
0x18002dabe  jns     short loc_18002DACA
0x18002dac0  mov     edx, 129h
0x18002dac5  jmp     loc_18002DA38
0x18002daca  mov     al, 1
0x18002dacc  jmp     loc_18002DA4A
```
