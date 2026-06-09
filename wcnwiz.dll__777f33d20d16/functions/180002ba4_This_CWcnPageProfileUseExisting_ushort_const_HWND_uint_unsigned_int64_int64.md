# _This<CWcnPageProfileUseExisting>(ushort const *,HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180002ba4`
- end: `0x180002bfb`
- name: `??$_This@VCWcnPageProfileUseExisting@@@@YAPEAVCWcnPageProfileUseExisting@@PEBGPEAUHWND__@@I_K_J@Z`
- size: `87`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpString@<rcx>, HWND hWnd@<rdx>, HANDLE hData)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a7d8`
- `0x18000a8e4`
- `0x18000a9f0`
- `0x18000aafc`
- `0x18000ac08`
- `0x18000ad14`
- `0x18000ae20`
- `0x18000b1b0`
- `0x18000b270`
- `0x18000b330`
- `0x18000b3f0`
- `0x18000b4b0`
- `0x18000b570`
- `0x18000b630`

## callees

- `0x180002ba4`

## import_xrefs

- `USER32!GetPropW` at `0x180002be9`
- `USER32!GetPropW` at `0x180002be9`
- `USER32!RemovePropW` at `0x180002be1`
- `USER32!RemovePropW` at `0x180002be1`
- `USER32!SetPropW` at `0x180002bcd`
- `USER32!SetPropW` at `0x180002bcd`

## pseudocode

```c
HANDLE __fastcall _This<CWcnPageProfileUseExisting>(LPCWSTR lpString, HWND hWnd, int a3, __int64 a4, _QWORD *hData)
{
  HANDLE v5; // rbx

  if ( a3 == 272 )
  {
    v5 = hData;
    if ( *(_DWORD *)hData == 104 )
      v5 = (HANDLE)hData[6];
    SetPropW(hWnd, lpString, v5);
  }
  else if ( a3 == 2 )
  {
    return RemovePropW(hWnd, lpString);
  }
  else
  {
    return GetPropW(hWnd, lpString);
  }
  return v5;
}

```

## disassembly

```asm
0x180002ba4  push    rbx
0x180002ba6  sub     rsp, 20h
0x180002baa  mov     rax, rdx
0x180002bad  cmp     r8d, 110h
0x180002bb4  jnz     short loc_180002BD5
0x180002bb6  mov     rbx, [rsp+28h+hData]
0x180002bbb  cmp     dword ptr [rbx], 68h ; 'h'
0x180002bbe  jnz     short loc_180002BC4
0x180002bc0  mov     rbx, [rbx+30h]
0x180002bc4  mov     rdx, rcx; lpString
0x180002bc7  mov     r8, rbx; hData
0x180002bca  mov     rcx, rax; hWnd
0x180002bcd  call    cs:__imp_SetPropW
0x180002bd3  jmp     short loc_180002BF2
0x180002bd5  mov     rdx, rcx; lpString
0x180002bd8  mov     rcx, rax; hWnd
0x180002bdb  cmp     r8d, 2
0x180002bdf  jnz     short loc_180002BE9
0x180002be1  call    cs:__imp_RemovePropW
0x180002be7  jmp     short loc_180002BEF
0x180002be9  call    cs:__imp_GetPropW
0x180002bef  mov     rbx, rax
0x180002bf2  mov     rax, rbx
0x180002bf5  add     rsp, 20h
0x180002bf9  pop     rbx
0x180002bfa  retn
```
