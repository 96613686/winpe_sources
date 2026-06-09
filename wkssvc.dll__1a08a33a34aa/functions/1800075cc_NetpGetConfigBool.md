# NetpGetConfigBool

- ea: `0x1800075cc`
- end: `0x180007764`
- name: `NetpGetConfigBool`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000776c`

## callees

- `0x1800075cc`
- `0x180007cb0`
- `0x180007cd4`
- `0x180007cf4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076f3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076ba`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076d4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800076f3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000765c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000765c`
- `netutils!NetApiBufferFree` at `0x18000772b`
- `netutils!NetApiBufferFree` at `0x18000772b`

## pseudocode

```c
__int64 __fastcall NetpGetConfigBool(HKEY *a1, const WCHAR *a2, int a3, int *a4)
{
  HKEY v8; // rcx
  __int64 result; // rax
  BYTE *lpData; // rbx
  LSTATUS v11; // eax
  unsigned int v12; // edi
  int v13; // edi
  __int64 v14; // rax
  unsigned int v15; // esi
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  if ( !a4 )
    return 87;
  *a4 = a3;
  if ( !a1 )
    return 87;
  v8 = *a1;
  Type = 0;
  cbData = 0;
  result = NetpGetWinRegConfigMaxSizes(v8, a2, &cbData);
  if ( !(_DWORD)result && cbData )
  {
    lpData = (BYTE *)NetpMemoryAllocate(cbData);
    if ( !lpData )
      return 8;
    v11 = RegQueryValueExW(*a1, a2, 0, &Type, lpData, &cbData);
    v12 = v11;
    if ( v11 == 2 )
    {
      v12 = 0;
LABEL_10:
      NetpMemoryFree(lpData);
      return v12;
    }
    if ( v11 )
      goto LABEL_10;
    v13 = 1;
    if ( Type == 1 )
    {
      if ( (unsigned int)_o__wcsicmp(lpData, L"TRUE") && (unsigned int)_o__wcsicmp(lpData, L"YES") )
      {
        if ( (unsigned int)_o__wcsicmp(lpData, L"FALSE") && (unsigned int)_o__wcsicmp(lpData, L"NO") )
        {
          v13 = a3;
          v14 = -1;
          do
            ++v14;
          while ( *(_WORD *)&lpData[2 * v14] );
          v15 = (_DWORD)v14 != 0 ? 0xD : 0;
          goto LABEL_23;
        }
        v13 = 0;
      }
LABEL_22:
      v15 = 0;
LABEL_23:
      NetApiBufferFree(lpData);
      result = v15;
      *a4 = v13;
      return result;
    }
    if ( Type == 4 )
    {
      v13 = *(_DWORD *)lpData;
      goto LABEL_22;
    }
    NetpMemoryFree(lpData);
    return 13;
  }
  return result;
}

```

## disassembly

```asm
0x1800075cc  mov     rax, rsp
0x1800075cf  mov     [rax+8], rbx
0x1800075d3  push    rbp
0x1800075d4  push    rsi
0x1800075d5  push    rdi
0x1800075d6  push    r14
0x1800075d8  push    r15
0x1800075da  sub     rsp, 30h
0x1800075de  xor     r15d, r15d
0x1800075e1  mov     r14, r9
0x1800075e4  mov     esi, r8d
0x1800075e7  mov     rbp, rdx
0x1800075ea  mov     rdi, rcx
0x1800075ed  test    r9, r9
0x1800075f0  jz      loc_18000774D
0x1800075f6  mov     [r9], r8d
0x1800075f9  test    rcx, rcx
0x1800075fc  jz      loc_18000774D
0x180007602  mov     rcx, [rcx]
0x180007605  lea     r8, [rax+18h]
0x180007609  mov     [rax+20h], r15d
0x18000760d  mov     [rax+18h], r15d
0x180007611  call    NetpGetWinRegConfigMaxSizes
0x180007616  test    eax, eax
0x180007618  jnz     loc_180007752
0x18000761e  mov     ecx, [rsp+58h+cbData]
0x180007622  test    ecx, ecx
0x180007624  jz      loc_180007752
0x18000762a  call    NetpMemoryAllocate
0x18000762f  mov     rbx, rax
0x180007632  test    rax, rax
0x180007635  jnz     short loc_18000763F
0x180007637  lea     eax, [rbx+8]
0x18000763a  jmp     loc_180007752
0x18000763f  mov     rcx, [rdi]; hKey
0x180007642  lea     rax, [rsp+58h+cbData]
0x180007647  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000764c  lea     r9, [rsp+58h+Type]; lpType
0x180007651  xor     r8d, r8d; lpReserved
0x180007654  mov     [rsp+58h+lpData], rbx; lpData
0x180007659  mov     rdx, rbp; lpValueName
0x18000765c  call    cs:__imp_RegQueryValueExW
0x180007663  nop     dword ptr [rax+rax+00h]
0x180007668  mov     edi, eax
0x18000766a  cmp     eax, 2
0x18000766d  jnz     short loc_180007674
0x18000766f  mov     edi, r15d
0x180007672  jmp     short loc_180007678
0x180007674  test    eax, eax
0x180007676  jz      short loc_180007687
0x180007678  mov     rcx, rbx
0x18000767b  call    NetpMemoryFree
0x180007680  mov     eax, edi
0x180007682  jmp     loc_180007752
0x180007687  mov     edi, 1
0x18000768c  cmp     [rsp+58h+Type], edi
0x180007690  jnz     loc_18000771C
0x180007696  lea     rdx, aTrue_0; "TRUE"
0x18000769d  mov     rcx, rbx
0x1800076a0  call    cs:__imp__o__wcsicmp
0x1800076a7  nop     dword ptr [rax+rax+00h]
0x1800076ac  test    eax, eax
0x1800076ae  jz      short loc_180007725
0x1800076b0  lea     rdx, aYes; "YES"
0x1800076b7  mov     rcx, rbx
0x1800076ba  call    cs:__imp__o__wcsicmp
0x1800076c1  nop     dword ptr [rax+rax+00h]
0x1800076c6  test    eax, eax
0x1800076c8  jz      short loc_180007725
0x1800076ca  lea     rdx, aFalse_0; "FALSE"
0x1800076d1  mov     rcx, rbx
0x1800076d4  call    cs:__imp__o__wcsicmp
0x1800076db  nop     dword ptr [rax+rax+00h]
0x1800076e0  test    eax, eax
0x1800076e2  jnz     short loc_1800076E9
0x1800076e4  mov     edi, r15d
0x1800076e7  jmp     short loc_180007725
0x1800076e9  lea     rdx, aNo; "NO"
0x1800076f0  mov     rcx, rbx
0x1800076f3  call    cs:__imp__o__wcsicmp
0x1800076fa  nop     dword ptr [rax+rax+00h]
0x1800076ff  test    eax, eax
0x180007701  jz      short loc_1800076E4
0x180007703  mov     edi, esi
0x180007705  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007709  inc     rax
0x18000770c  cmp     [rbx+rax*2], r15w
0x180007711  jnz     short loc_180007709
0x180007713  neg     eax
0x180007715  sbb     esi, esi
0x180007717  and     esi, 0Dh
0x18000771a  jmp     short loc_180007728
0x18000771c  cmp     [rsp+58h+Type], 4
0x180007721  jnz     short loc_18000773E
0x180007723  mov     edi, [rbx]
0x180007725  mov     esi, r15d
0x180007728  mov     rcx, rbx; Buffer
0x18000772b  call    cs:__imp_NetApiBufferFree
0x180007732  nop     dword ptr [rax+rax+00h]
0x180007737  mov     eax, esi
0x180007739  mov     [r14], edi
0x18000773c  jmp     short loc_180007752
0x18000773e  mov     rcx, rbx
0x180007741  call    NetpMemoryFree
0x180007746  mov     eax, 0Dh
0x18000774b  jmp     short loc_180007752
0x18000774d  mov     eax, 57h ; 'W'
0x180007752  mov     rbx, [rsp+58h+arg_0]
0x180007757  add     rsp, 30h
0x18000775b  pop     r15
0x18000775d  pop     r14
0x18000775f  pop     rdi
0x180007760  pop     rsi
0x180007761  pop     rbp
0x180007762  retn
```
