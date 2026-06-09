# ConvertStringSDToSDDomainW

- ea: `0x180021820`
- end: `0x1800218bc`
- name: `ConvertStringSDToSDDomainW`
- size: `156`
- prototype: `__int64 __usercall@<rax>(__int64@<rcx>, __int64@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180021720`

## callees

- `0x180005d00`
- `0x180021820`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18002184e`
- `ntdll!RtlValidSid` at `0x180021860`
- `ntdll!RtlValidSid` at `0x18002184e`
- `ntdll!RtlValidSid` at `0x180021860`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800218a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800218a4`

## pseudocode

```c
_BOOL8 __fastcall ConvertStringSDToSDDomainW(_BYTE *a1, _BYTE *a2, wchar_t *a3, int a4, HLOCAL *a5, ULONG *a6)
{
  DWORD v10; // ebx

  if ( a3 && a5 && a1 && RtlValidSid(a1) && (!a2 || RtlValidSid(a2)) )
  {
    if ( a4 == 1 )
      v10 = LocalConvertStringSDToSD_Rev1(a2, a1, 0, a3, a5, a6);
    else
      v10 = 1305;
  }
  else
  {
    v10 = 87;
  }
  SetLastError(v10);
  return v10 == 0;
}

```

## disassembly

```asm
0x180021820  push    rbx
0x180021822  push    rbp
0x180021823  push    rsi
0x180021824  push    rdi
0x180021825  push    r14
0x180021827  sub     rsp, 30h
0x18002182b  mov     esi, r9d
0x18002182e  mov     r14, r8
0x180021831  mov     rbx, rdx
0x180021834  mov     rdi, rcx
0x180021837  test    r8, r8
0x18002183a  jz      short loc_18002189D
0x18002183c  mov     rbp, [rsp+58h+arg_20]
0x180021844  test    rbp, rbp
0x180021847  jz      short loc_18002189D
0x180021849  test    rcx, rcx
0x18002184c  jz      short loc_18002189D
0x18002184e  call    cs:__imp_RtlValidSid
0x180021854  test    al, al
0x180021856  jz      short loc_18002189D
0x180021858  test    rbx, rbx
0x18002185b  jz      short loc_18002186A
0x18002185d  mov     rcx, rbx; Sid
0x180021860  call    cs:__imp_RtlValidSid
0x180021866  test    al, al
0x180021868  jz      short loc_18002189D
0x18002186a  cmp     esi, 1
0x18002186d  jz      short loc_180021876
0x18002186f  mov     ebx, 519h
0x180021874  jmp     short loc_1800218A2
0x180021876  mov     rax, [rsp+58h+arg_28]
0x18002187e  mov     r9, r14
0x180021881  mov     [rsp+58h+var_30], rax; __int64
0x180021886  xor     r8d, r8d
0x180021889  mov     rdx, rdi; __int64
0x18002188c  mov     [rsp+58h+var_38], rbp; __int64
0x180021891  mov     rcx, rbx; __int64
0x180021894  call    LocalConvertStringSDToSD_Rev1
0x180021899  mov     ebx, eax
0x18002189b  jmp     short loc_1800218A2
0x18002189d  mov     ebx, 57h ; 'W'
0x1800218a2  mov     ecx, ebx; dwErrCode
0x1800218a4  call    cs:__imp_SetLastError
0x1800218aa  xor     eax, eax
0x1800218ac  test    ebx, ebx
0x1800218ae  setz    al
0x1800218b1  add     rsp, 30h
0x1800218b5  pop     r14
0x1800218b7  pop     rdi
0x1800218b8  pop     rsi
0x1800218b9  pop     rbp
0x1800218ba  pop     rbx
0x1800218bb  retn
```
