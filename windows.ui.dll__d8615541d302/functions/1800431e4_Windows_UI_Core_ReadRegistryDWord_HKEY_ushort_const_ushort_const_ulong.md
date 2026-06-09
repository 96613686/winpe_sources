# Windows::UI::Core::ReadRegistryDWord(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x1800431e4`
- end: `0x1800432d4`
- name: `?ReadRegistryDWord@Core@UI@Windows@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `240`
- prototype: `int(Windows::UI::Core *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c3c4`
- `0x18006f264`

## callees

- `0x1800431e4`
- `0x18007f61c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043262`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043262`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004322b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004322b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043270`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043270`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::ReadRegistryDWord(
        Windows::UI::Core *this,
        const WCHAR *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned int v6; // ebx
  DWORD cbData; // [rsp+30h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-8h] BYREF
  Windows::UI::Core *Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  Data = this;
  *(_DWORD *)a4 = 0;
  hKey = 0;
  v6 = -2147418113;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey) )
  {
    Type = 0;
    LODWORD(Data) = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, a3, 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)&WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids,
          (_DWORD)a3,
          (char)Data);
      }
      v6 = 0;
      *(_DWORD *)a4 = (_DWORD)Data;
    }
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x1800431e4  mov     [rsp-18h+arg_8], rbx
0x1800431e9  mov     [rsp-18h+Data], rcx
0x1800431ee  push    rbp
0x1800431ef  push    rsi
0x1800431f0  push    rdi
0x1800431f1  mov     rbp, rsp
0x1800431f4  sub     rsp, 40h
0x1800431f8  mov     rsi, r9
0x1800431fb  mov     dword ptr [r9], 0
0x180043202  mov     rdi, r8
0x180043205  mov     [rbp+hKey], 0
0x18004320d  lea     rax, [rbp+hKey]
0x180043211  mov     r9d, 20019h; samDesired
0x180043217  xor     r8d, r8d; ulOptions
0x18004321a  mov     [rsp+40h+phkResult], rax; phkResult
0x18004321f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043226  mov     ebx, 8000FFFFh
0x18004322b  call    cs:__imp_RegOpenKeyExW
0x180043231  test    eax, eax
0x180043233  jnz     short loc_180043276
0x180043235  mov     rcx, [rbp+hKey]; hKey
0x180043239  lea     r9, [rbp+Type]; lpType
0x18004323d  mov     [rbp+Type], eax
0x180043240  xor     r8d, r8d; lpReserved
0x180043243  mov     dword ptr [rbp+Data], eax
0x180043246  mov     rdx, rdi; lpValueName
0x180043249  lea     rax, [rbp+cbData]
0x18004324d  mov     [rbp+cbData], 4
0x180043254  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180043259  lea     rax, [rbp+Data]
0x18004325d  mov     [rsp+40h+phkResult], rax; lpData
0x180043262  call    cs:__imp_RegQueryValueExW
0x180043268  test    eax, eax
0x18004326a  jz      short loc_180043285
0x18004326c  mov     rcx, [rbp+hKey]; hKey
0x180043270  call    cs:__imp_RegCloseKey
0x180043276  mov     eax, ebx
0x180043278  mov     rbx, [rsp+40h+arg_8]
0x18004327d  add     rsp, 40h
0x180043281  pop     rdi
0x180043282  pop     rsi
0x180043283  pop     rbp
0x180043284  retn
0x180043285  cmp     [rbp+Type], 4
0x180043289  jnz     short loc_18004326C
0x18004328b  mov     rcx, cs:WPP_GLOBAL_Control
0x180043292  lea     rax, WPP_GLOBAL_Control
0x180043299  cmp     rcx, rax
0x18004329c  jnz     short loc_1800432A7
0x18004329e  mov     eax, dword ptr [rbp+Data]
0x1800432a1  xor     ebx, ebx
0x1800432a3  mov     [rsi], eax
0x1800432a5  jmp     short loc_18004326C
0x1800432a7  test    byte ptr [rcx+1Ch], 20h
0x1800432ab  jz      short loc_18004329E
0x1800432ad  cmp     byte ptr [rcx+19h], 5
0x1800432b1  jb      short loc_18004329E
0x1800432b3  mov     eax, dword ptr [rbp+Data]
0x1800432b6  lea     r8, WPP_aa59c5c688db31e5073921c5d0e6552c_Traceguids
0x1800432bd  mov     rcx, [rcx+10h]
0x1800432c1  mov     edx, 0Ah
0x1800432c6  mov     r9, rdi
0x1800432c9  mov     dword ptr [rsp+40h+phkResult], eax
0x1800432cd  call    WPP_SF_Sd
0x1800432d2  jmp     short loc_18004329E
```
