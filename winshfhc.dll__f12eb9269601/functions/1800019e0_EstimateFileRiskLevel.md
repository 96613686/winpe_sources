# EstimateFileRiskLevel

- ea: `0x1800019e0`
- end: `0x180001aca`
- name: `EstimateFileRiskLevel`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001948`
- `0x1800019e0`
- `0x180002ae0`

## string_xrefs

- `0x180001a3e`: `shimgvw.dll`

## pseudocode

```c
__int64 __fastcall EstimateFileRiskLevel(__int64 a1, const unsigned __int16 *a2, __int64 a3, _DWORD *a4)
{
  __int64 result; // rax
  unsigned __int16 *v7; // [rsp+48h] [rbp+20h] BYREF

  if ( !a4 || !a2 || !a1 || !a3 )
    return 2147942487LL;
  *a4 = 0;
  v7 = 0;
  result = CommonUtil::UtilGetFilenameFromPath<unsigned short>(a3, &v7);
  if ( (int)result >= 0 )
  {
    if ( (unsigned int)fhc_mask_match(L"shimgvw.dll", v7)
      || (unsigned int)fhc_mask_match(L"notepad.exe", v7)
      || (unsigned int)fhc_mask_match(L"jpg", a2)
      || (unsigned int)fhc_mask_match(L"jpeg", a2)
      || (unsigned int)fhc_mask_match(L".jpg", a2)
      || (unsigned int)fhc_mask_match(L".jpeg", a2) )
    {
      *a4 = 1;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800019e0  mov     [rsp+arg_0], rbx
0x1800019e5  push    rdi
0x1800019e6  sub     rsp, 20h
0x1800019ea  mov     rdi, r9
0x1800019ed  mov     rbx, rdx
0x1800019f0  test    r9, r9
0x1800019f3  jz      loc_180001AB9
0x1800019f9  test    rdx, rdx
0x1800019fc  jz      loc_180001AB9
0x180001a02  test    rcx, rcx
0x180001a05  jz      loc_180001AB9
0x180001a0b  test    r8, r8
0x180001a0e  jz      loc_180001AB9
0x180001a14  lea     rdx, [rsp+28h+arg_18]
0x180001a19  mov     dword ptr [r9], 0
0x180001a20  mov     rcx, r8
0x180001a23  mov     [rsp+28h+arg_18], 0
0x180001a2c  call    ??$UtilGetFilenameFromPath@G@CommonUtil@@YAJPEBGPEAPEBGPEA_K@Z; CommonUtil::UtilGetFilenameFromPath<ushort>(ushort const *,ushort const * *,unsigned __int64 *)
0x180001a31  test    eax, eax
0x180001a33  js      loc_180001ABE
0x180001a39  mov     rdx, [rsp+28h+arg_18]; unsigned __int16 *
0x180001a3e  lea     rcx, aShimgvwDll; "shimgvw.dll"
0x180001a45  call    ?fhc_mask_match@@YAHPEBG0@Z; fhc_mask_match(ushort const *,ushort const *)
0x180001a4a  test    eax, eax
0x180001a4c  jnz     short loc_180001AAF
0x180001a4e  mov     rdx, [rsp+28h+arg_18]; unsigned __int16 *
0x180001a53  lea     rcx, aNotepadExe; "notepad.exe"
0x180001a5a  call    ?fhc_mask_match@@YAHPEBG0@Z; fhc_mask_match(ushort const *,ushort const *)
0x180001a5f  test    eax, eax
0x180001a61  jnz     short loc_180001AAF
0x180001a63  mov     rdx, rbx; unsigned __int16 *
0x180001a66  lea     rcx, aJpg; "jpg"
0x180001a6d  call    ?fhc_mask_match@@YAHPEBG0@Z; fhc_mask_match(ushort const *,ushort const *)
0x180001a72  test    eax, eax
0x180001a74  jnz     short loc_180001AAF
0x180001a76  mov     rdx, rbx; unsigned __int16 *
0x180001a79  lea     rcx, aJpeg; "jpeg"
0x180001a80  call    ?fhc_mask_match@@YAHPEBG0@Z; fhc_mask_match(ushort const *,ushort const *)
0x180001a85  test    eax, eax
0x180001a87  jnz     short loc_180001AAF
0x180001a89  mov     rdx, rbx; unsigned __int16 *
0x180001a8c  lea     rcx, aJpg_0; ".jpg"
0x180001a93  call    ?fhc_mask_match@@YAHPEBG0@Z; fhc_mask_match(ushort const *,ushort const *)
0x180001a98  test    eax, eax
0x180001a9a  jnz     short loc_180001AAF
0x180001a9c  mov     rdx, rbx; unsigned __int16 *
0x180001a9f  lea     rcx, aJpeg_0; ".jpeg"
0x180001aa6  call    ?fhc_mask_match@@YAHPEBG0@Z; fhc_mask_match(ushort const *,ushort const *)
0x180001aab  test    eax, eax
0x180001aad  jz      short loc_180001AB5
0x180001aaf  mov     dword ptr [rdi], 1
0x180001ab5  xor     eax, eax
0x180001ab7  jmp     short loc_180001ABE
0x180001ab9  mov     eax, 80070057h
0x180001abe  mov     rbx, [rsp+28h+arg_0]
0x180001ac3  add     rsp, 20h
0x180001ac7  pop     rdi
0x180001ac8  retn
```
