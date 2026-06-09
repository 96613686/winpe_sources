# SampDsMakeSpnW(ushort *,ushort *,ushort *,ushort,ushort *,ushort * *)

- ea: `0x180015d48`
- end: `0x180015e10`
- name: `?SampDsMakeSpnW@@YAJPEAG00G0PEAPEAG@Z`
- size: `200`
- prototype: `__int64 __usercall@<rax>(LPCWSTR ServiceClass@<rcx>, LPCWSTR ServiceName@<rdx>, unsigned __int16 *@<r8>, unsigned __int16@<r9w>, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180005ca0`
- `0x180016288`

## callees

- `0x180015d48`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015df8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015df8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015dac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015dac`
- `DSPARSE!DsMakeSpnW` at `0x180015d8b`
- `DSPARSE!DsMakeSpnW` at `0x180015de6`
- `DSPARSE!DsMakeSpnW` at `0x180015d8b`
- `DSPARSE!DsMakeSpnW` at `0x180015de6`

## pseudocode

```c
__int64 __fastcall SampDsMakeSpnW(
        LPCWSTR ServiceClass,
        LPCWSTR ServiceName,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 **a6)
{
  HLOCAL *v6; // rdi
  unsigned int v9; // ebx
  WCHAR *pszSpn; // rax
  DWORD pcSpnLength; // [rsp+88h] [rbp+20h] BYREF

  v6 = (HLOCAL *)a6;
  pcSpnLength = 0;
  *a6 = 0;
  if ( DsMakeSpnW(ServiceClass, ServiceName, 0, 0, 0, &pcSpnLength, 0) != 111 )
  {
    v9 = -1073741811;
LABEL_7:
    LocalFree(*v6);
    *v6 = 0;
    return v9;
  }
  pszSpn = (WCHAR *)LocalAlloc(0x40u, 2LL * pcSpnLength);
  *v6 = pszSpn;
  if ( !pszSpn )
  {
    v9 = -1073741801;
    goto LABEL_7;
  }
  v9 = 0;
  if ( DsMakeSpnW(ServiceClass, ServiceName, 0, 0, 0, &pcSpnLength, pszSpn) )
  {
    v9 = -1073741595;
    goto LABEL_7;
  }
  return v9;
}

```

## disassembly

```asm
0x180015d48  mov     r11, rsp
0x180015d4b  mov     [r11+20h], r9w
0x180015d50  push    rbx
0x180015d51  push    rbp
0x180015d52  push    rsi
0x180015d53  push    rdi
0x180015d54  sub     rsp, 48h
0x180015d58  mov     rdi, [rsp+68h+arg_28]
0x180015d60  lea     rax, [r11+20h]
0x180015d64  xor     r9d, r9d; InstancePort
0x180015d67  mov     dword ptr [r11+20h], 0
0x180015d6f  mov     [r11-38h], r9
0x180015d73  xor     r8d, r8d; InstanceName
0x180015d76  mov     [r11-40h], rax
0x180015d7a  mov     rsi, rdx
0x180015d7d  mov     qword ptr [rdi], 0
0x180015d84  mov     rbp, rcx
0x180015d87  mov     [r11-48h], r9
0x180015d8b  call    cs:__imp_DsMakeSpnW
0x180015d91  cmp     eax, 6Fh ; 'o'
0x180015d94  jz      short loc_180015D9D
0x180015d96  mov     ebx, 0C000000Dh
0x180015d9b  jmp     short loc_180015DF5
0x180015d9d  mov     edx, [rsp+68h+arg_18]
0x180015da4  mov     ecx, 40h ; '@'; uFlags
0x180015da9  add     rdx, rdx; uBytes
0x180015dac  call    cs:__imp_LocalAlloc
0x180015db2  mov     [rdi], rax
0x180015db5  test    rax, rax
0x180015db8  jnz     short loc_180015DC1
0x180015dba  mov     ebx, 0C0000017h
0x180015dbf  jmp     short loc_180015DF5
0x180015dc1  mov     [rsp+68h+pszSpn], rax; pszSpn
0x180015dc6  xor     ebx, ebx
0x180015dc8  lea     rax, [rsp+68h+arg_18]
0x180015dd0  xor     r9d, r9d; InstancePort
0x180015dd3  mov     [rsp+68h+pcSpnLength], rax; pcSpnLength
0x180015dd8  xor     r8d, r8d; InstanceName
0x180015ddb  mov     rdx, rsi; ServiceName
0x180015dde  mov     [rsp+68h+Referrer], rbx; Referrer
0x180015de3  mov     rcx, rbp; ServiceClass
0x180015de6  call    cs:__imp_DsMakeSpnW
0x180015dec  test    eax, eax
0x180015dee  jz      short loc_180015E05
0x180015df0  mov     ebx, 0C00000E5h
0x180015df5  mov     rcx, [rdi]; hMem
0x180015df8  call    cs:__imp_LocalFree
0x180015dfe  mov     qword ptr [rdi], 0
0x180015e05  mov     eax, ebx
0x180015e07  add     rsp, 48h
0x180015e0b  pop     rdi
0x180015e0c  pop     rsi
0x180015e0d  pop     rbp
0x180015e0e  pop     rbx
0x180015e0f  retn
```
