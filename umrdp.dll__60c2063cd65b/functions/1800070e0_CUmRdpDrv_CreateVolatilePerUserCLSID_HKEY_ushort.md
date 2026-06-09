# CUmRdpDrv::CreateVolatilePerUserCLSID(HKEY__ *,ushort *)

- ea: `0x1800070e0`
- end: `0x1800072e6`
- name: `?CreateVolatilePerUserCLSID@CUmRdpDrv@@AEAAHPEAUHKEY__@@PEAG@Z`
- size: `518`
- prototype: `int(CUmRdpDrv *__hidden this, HKEY, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180018624`

## callees

- `0x1800070e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000712f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800071b5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000712f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800071b5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007272`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007272`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000728d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000728d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800072a3`
- `SHLWAPI!SHDeleteKeyW` at `0x1800072c3`
- `SHLWAPI!SHDeleteKeyW` at `0x1800072c3`

## pseudocode

```c
__int64 __fastcall CUmRdpDrv::CreateVolatilePerUserCLSID(CUmRdpDrv *this, HKEY a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // esi
  const WCHAR *v8; // rdx
  LSTATUS v9; // eax
  HKEY v10; // rcx
  HKEY v11; // rbp
  __int64 v12; // rdi
  DWORD v13; // r15d
  const BYTE *p_Data; // r9
  DWORD v15; // edx
  __int64 v16; // r10
  _WORD *v17; // rax
  LSTATUS v18; // eax
  unsigned int v19; // edx
  HKEY hKey; // [rsp+50h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-30h] BYREF
  int Data; // [rsp+A8h] [rbp+20h] BYREF

  hKey = 0;
  if ( RegCreateKeyExW(a2, a3, 0, 0, 1u, 0x20006u, 0, &hKey, 0) )
    return 0;
  v6 = 0;
  v7 = 1;
  while ( v7 )
  {
    phkResult = 0;
    v8 = (const WCHAR *)*((_QWORD *)this + 4 * v6 + 68);
    if ( !v8 || !*v8 )
    {
      v10 = hKey;
      v11 = 0;
      phkResult = hKey;
LABEL_9:
      v12 = 32LL * v6;
      Data = 0;
      v13 = *(_DWORD *)((char *)this + v12 + 560);
      if ( v13 == 4 )
      {
        p_Data = (const BYTE *)&Data;
        Data = *(_DWORD *)((char *)this + v12 + 568);
        v15 = 4;
      }
      else
      {
        p_Data = 0;
        v15 = 0;
        if ( *(_QWORD *)((char *)this + v12 + 568) )
        {
          v16 = 0x7FFFFFFF;
          v17 = *(_WORD **)((char *)this + v12 + 568);
          do
          {
            if ( !*v17 )
              break;
            ++v17;
            --v16;
          }
          while ( v16 );
          if ( v16 )
          {
            v15 = 2 * (0x7FFFFFFF - v16) + 2;
            p_Data = *(const BYTE **)((char *)this + v12 + 568);
          }
        }
      }
      v18 = RegSetValueExW(v10, *(LPCWSTR *)((char *)this + v12 + 552), 0, v13, p_Data, v15);
      v19 = 0;
      if ( !v18 )
        v19 = v7;
      v7 = v19;
      if ( v11 )
        RegCloseKey(v11);
      goto LABEL_21;
    }
    v9 = RegCreateKeyExW(hKey, v8, 0, 0, 1u, 0x20006u, 0, &phkResult, 0);
    v10 = phkResult;
    v11 = phkResult;
    if ( !v9 )
      goto LABEL_9;
    v7 = 0;
LABEL_21:
    if ( ++v6 >= 0xF )
      break;
  }
  RegCloseKey(hKey);
  if ( !v7 )
    SHDeleteKeyW(a2, a3);
  return v7;
}

```

## disassembly

```asm
0x1800070e0  push    rbx
0x1800070e2  push    r12
0x1800070e4  push    r13
0x1800070e6  push    r14
0x1800070e8  push    r15
0x1800070ea  sub     rsp, 60h
0x1800070ee  xor     r15d, r15d
0x1800070f1  lea     rax, [rsp+88h+hKey]
0x1800070f6  mov     [rsp+88h+lpdwDisposition], r15; lpdwDisposition
0x1800070fb  mov     r12, r8
0x1800070fe  mov     [rsp+88h+phkResult], rax; phkResult
0x180007103  mov     r13, rdx
0x180007106  mov     [rsp+88h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18000710b  mov     r14, rcx
0x18000710e  mov     [rsp+88h+samDesired], 20006h; samDesired
0x180007116  xor     r9d, r9d; lpClass
0x180007119  xor     r8d, r8d; Reserved
0x18000711c  mov     [rsp+88h+dwOptions], 1; dwOptions
0x180007124  mov     rdx, r12; lpSubKey
0x180007127  mov     [rsp+88h+hKey], r15
0x18000712c  mov     rcx, r13; hKey
0x18000712f  call    cs:__imp_RegCreateKeyExW
0x180007135  test    eax, eax
0x180007137  jnz     loc_1800072E1
0x18000713d  mov     [rsp+88h+arg_8], rsi
0x180007145  mov     ebx, r15d
0x180007148  mov     [rsp+88h+arg_0], rbp
0x180007150  mov     esi, 1
0x180007155  mov     [rsp+88h+arg_10], rdi
0x18000715d  nop     dword ptr [rax]
0x180007160  test    esi, esi
0x180007162  jz      loc_18000729E
0x180007168  mov     edi, ebx
0x18000716a  mov     [rsp+88h+var_30], r15
0x18000716f  lea     rax, [rdi+11h]
0x180007173  shl     rax, 5
0x180007177  mov     rdx, [rax+r14]; lpSubKey
0x18000717b  test    rdx, rdx
0x18000717e  jz      short loc_1800071CF
0x180007180  cmp     word ptr [rdx], 0
0x180007184  jz      short loc_1800071CF
0x180007186  mov     rcx, [rsp+88h+hKey]; hKey
0x18000718b  lea     rax, [rsp+88h+var_30]
0x180007190  mov     [rsp+88h+lpdwDisposition], r15; lpdwDisposition
0x180007195  xor     r9d, r9d; lpClass
0x180007198  mov     [rsp+88h+phkResult], rax; phkResult
0x18000719d  xor     r8d, r8d; Reserved
0x1800071a0  mov     [rsp+88h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800071a5  mov     [rsp+88h+samDesired], 20006h; samDesired
0x1800071ad  mov     [rsp+88h+dwOptions], 1; dwOptions
0x1800071b5  call    cs:__imp_RegCreateKeyExW
0x1800071bb  mov     rcx, [rsp+88h+var_30]
0x1800071c0  mov     rbp, rcx
0x1800071c3  test    eax, eax
0x1800071c5  jz      short loc_1800071DC
0x1800071c7  mov     esi, r15d
0x1800071ca  jmp     loc_180007293
0x1800071cf  mov     rcx, [rsp+88h+hKey]; hKey
0x1800071d4  mov     rbp, r15
0x1800071d7  mov     [rsp+88h+var_30], rcx
0x1800071dc  shl     rdi, 5
0x1800071e0  mov     [rsp+88h+Data], r15d
0x1800071e8  mov     r15d, [rdi+r14+230h]
0x1800071f0  cmp     r15d, 4
0x1800071f4  jnz     short loc_180007212
0x1800071f6  mov     eax, [rdi+r14+238h]
0x1800071fe  lea     r9, [rsp+88h+Data]
0x180007206  mov     [rsp+88h+Data], eax
0x18000720d  mov     edx, r15d
0x180007210  jmp     short loc_18000725B
0x180007212  mov     r11, [rdi+r14+238h]
0x18000721a  xor     r9d, r9d
0x18000721d  xor     edx, edx
0x18000721f  test    r11, r11
0x180007222  jz      short loc_18000725B
0x180007224  mov     r10d, 7FFFFFFFh
0x18000722a  mov     rax, r11
0x18000722d  cmp     [rax], dx
0x180007230  jz      short loc_18000723C
0x180007232  add     rax, 2
0x180007236  sub     r10, 1
0x18000723a  jnz     short loc_18000722D
0x18000723c  xor     eax, eax
0x18000723e  mov     r8d, 7FFFFFFFh
0x180007244  sub     r8, r10
0x180007247  test    r10, r10
0x18000724a  cmovz   r8, rax
0x18000724e  jz      short loc_18000725B
0x180007250  lea     edx, ds:2[r8*2]
0x180007258  mov     r9, r11
0x18000725b  mov     [rsp+88h+samDesired], edx; cbData
0x18000725f  xor     r8d, r8d; Reserved
0x180007262  mov     rdx, [rdi+r14+228h]; lpValueName
0x18000726a  mov     qword ptr [rsp+88h+dwOptions], r9; lpData
0x18000726f  mov     r9d, r15d; dwType
0x180007272  call    cs:__imp_RegSetValueExW
0x180007278  xor     r15d, r15d
0x18000727b  test    eax, eax
0x18000727d  mov     edx, r15d
0x180007280  cmovz   edx, esi
0x180007283  mov     esi, edx
0x180007285  test    rbp, rbp
0x180007288  jz      short loc_180007293
0x18000728a  mov     rcx, rbp; hKey
0x18000728d  call    cs:__imp_RegCloseKey
0x180007293  inc     ebx
0x180007295  cmp     ebx, 0Fh
0x180007298  jb      loc_180007160
0x18000729e  mov     rcx, [rsp+88h+hKey]; hKey
0x1800072a3  call    cs:__imp_RegCloseKey
0x1800072a9  mov     rdi, [rsp+88h+arg_10]
0x1800072b1  mov     rbp, [rsp+88h+arg_0]
0x1800072b9  test    esi, esi
0x1800072bb  jnz     short loc_1800072C9
0x1800072bd  mov     rdx, r12; pszSubKey
0x1800072c0  mov     rcx, r13; hkey
0x1800072c3  call    cs:__imp_SHDeleteKeyW
0x1800072c9  mov     eax, esi
0x1800072cb  mov     rsi, [rsp+88h+arg_8]
0x1800072d3  add     rsp, 60h
0x1800072d7  pop     r15
0x1800072d9  pop     r14
0x1800072db  pop     r13
0x1800072dd  pop     r12
0x1800072df  pop     rbx
0x1800072e0  retn
0x1800072e1  mov     eax, r15d
0x1800072e4  jmp     short loc_1800072D3
```
