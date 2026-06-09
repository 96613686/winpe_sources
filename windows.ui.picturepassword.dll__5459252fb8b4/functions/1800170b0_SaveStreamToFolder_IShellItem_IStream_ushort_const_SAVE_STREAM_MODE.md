# SaveStreamToFolder(IShellItem *,IStream *,ushort const *,SAVE_STREAM_MODE)

- ea: `0x1800170b0`
- end: `0x180017205`
- name: `?SaveStreamToFolder@@YAJPEAUIShellItem@@PEAUIStream@@PEBGW4SAVE_STREAM_MODE@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64 *, IStream *, IStream *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001720c`

## callees

- `0x1800170b0`
- `0x18001f010`

## import_xrefs

- `SHCORE!IStream_Size` at `0x18001716a`
- `SHCORE!IStream_Size` at `0x18001716a`
- `SHCORE!IStream_Copy` at `0x18001718e`
- `SHCORE!IStream_Copy` at `0x18001718e`

## pseudocode

```c
__int64 __fastcall SaveStreamToFolder(__int64 *a1, IStream *a2, IStream *a3)
{
  __int64 v3; // rax
  HRESULT v5; // ebx
  IStream *v6; // rcx
  ULARGE_INTEGER pui; // [rsp+40h] [rbp-10h] BYREF
  __int64 v9; // [rsp+60h] [rbp+10h] BYREF
  IStream *pstmTo; // [rsp+70h] [rbp+20h] BYREF

  pstmTo = a3;
  v3 = *a1;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, const GUID *, GUID *, __int64 *))(v3 + 24))(
         a1,
         0,
         &BHID_SFObject,
         &GUID_0000000b_0000_0000_c000_000000000046,
         &v9);
  if ( v5 >= 0 )
  {
    pstmTo = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, const WCHAR *, __int64, _QWORD, _DWORD, IStream **))(*(_QWORD *)v9 + 24LL))(
           v9,
           L"background.png",
           69633,
           0,
           0,
           &pstmTo);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)pstmTo + 48LL))(pstmTo, 0);
      if ( v5 >= 0 )
      {
        pui.QuadPart = 0;
        v5 = IStream_Size(a2, &pui);
        if ( v5 >= 0 )
        {
          if ( pui.HighPart )
          {
            v5 = -2147317563;
          }
          else
          {
            v5 = IStream_Copy(a2, pstmTo, pui.LowPart);
            if ( v5 >= 0 )
            {
              v5 = (*(__int64 (__fastcall **)(IStream *, _QWORD))(*(_QWORD *)pstmTo + 64LL))(pstmTo, 0);
              if ( v5 >= 0 )
                v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 72LL))(v9, 0);
            }
          }
        }
      }
    }
    v6 = pstmTo;
    pstmTo = 0;
    if ( v6 )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800170b0  mov     r11, rsp
0x1800170b3  mov     [r11+10h], rbx
0x1800170b7  mov     [r11+20h], rdi
0x1800170bb  mov     [r11+18h], r8
0x1800170bf  push    rbp
0x1800170c0  mov     rbp, rsp
0x1800170c3  sub     rsp, 50h
0x1800170c7  mov     rax, [rcx]
0x1800170ca  lea     r9, _GUID_0000000b_0000_0000_c000_000000000046
0x1800170d1  mov     rdi, rdx
0x1800170d4  mov     [rbp+arg_0], 0
0x1800170dc  lea     rdx, [rbp+arg_0]
0x1800170e0  mov     [r11-38h], rdx
0x1800170e4  lea     r8, BHID_SFObject
0x1800170eb  mov     rax, [rax+18h]
0x1800170ef  xor     edx, edx
0x1800170f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170f6  mov     ebx, eax
0x1800170f8  test    eax, eax
0x1800170fa  js      loc_1800171F3
0x180017100  mov     rcx, [rbp+arg_0]
0x180017104  lea     rdx, [rbp+pstmTo]
0x180017108  mov     [rsp+50h+var_28], rdx
0x18001710d  xor     r9d, r9d
0x180017110  mov     [rbp+pstmTo], 0
0x180017118  lea     rdx, pszMore; "background.png"
0x18001711f  mov     r8d, 11001h
0x180017125  mov     [rsp+50h+var_30], 0
0x18001712d  mov     rax, [rcx]
0x180017130  mov     rax, [rax+18h]
0x180017134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017139  mov     ebx, eax
0x18001713b  test    eax, eax
0x18001713d  js      loc_1800171C6
0x180017143  mov     rcx, [rbp+pstmTo]
0x180017147  xor     edx, edx
0x180017149  mov     rax, [rcx]
0x18001714c  mov     rax, [rax+30h]
0x180017150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017155  mov     ebx, eax
0x180017157  test    eax, eax
0x180017159  js      short loc_1800171C6
0x18001715b  lea     rdx, [rbp+pui]; pui
0x18001715f  mov     qword ptr [rbp+pui], 0
0x180017167  mov     rcx, rdi; pstm
0x18001716a  call    cs:__imp_IStream_Size
0x180017170  mov     ebx, eax
0x180017172  test    eax, eax
0x180017174  js      short loc_1800171C6
0x180017176  cmp     dword ptr [rbp+pui+4], 0
0x18001717a  jz      short loc_180017183
0x18001717c  mov     ebx, 800288C5h
0x180017181  jmp     short loc_1800171C6
0x180017183  mov     r8d, dword ptr [rbp+pui]; cb
0x180017187  mov     rcx, rdi; pstmFrom
0x18001718a  mov     rdx, [rbp+pstmTo]; pstmTo
0x18001718e  call    cs:__imp_IStream_Copy
0x180017194  mov     ebx, eax
0x180017196  test    eax, eax
0x180017198  js      short loc_1800171C6
0x18001719a  mov     rcx, [rbp+pstmTo]
0x18001719e  xor     edx, edx
0x1800171a0  mov     rax, [rcx]
0x1800171a3  mov     rax, [rax+40h]
0x1800171a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171ac  mov     ebx, eax
0x1800171ae  test    eax, eax
0x1800171b0  js      short loc_1800171C6
0x1800171b2  mov     rcx, [rbp+arg_0]
0x1800171b6  xor     edx, edx
0x1800171b8  mov     rax, [rcx]
0x1800171bb  mov     rax, [rax+48h]
0x1800171bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171c4  mov     ebx, eax
0x1800171c6  mov     rcx, [rbp+pstmTo]
0x1800171ca  mov     [rbp+pstmTo], 0
0x1800171d2  test    rcx, rcx
0x1800171d5  jz      short loc_1800171E3
0x1800171d7  mov     rax, [rcx]
0x1800171da  mov     rax, [rax+10h]
0x1800171de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e3  mov     rcx, [rbp+arg_0]
0x1800171e7  mov     rax, [rcx]
0x1800171ea  mov     rax, [rax+10h]
0x1800171ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171f3  mov     rdi, [rsp+50h+arg_18]
0x1800171f8  mov     eax, ebx
0x1800171fa  mov     rbx, [rsp+50h+arg_8]
0x1800171ff  add     rsp, 50h
0x180017203  pop     rbp
0x180017204  retn
```
