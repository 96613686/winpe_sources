# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>,>(void)

- ea: `0x18002f574`
- end: `0x18002f6e7`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `371`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002f458`

## callees

- `0x1800086c4`
- `0x18002f574`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002f660`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18002f660`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f58b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f58b`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x158u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &tip2::details::test_data_interface::`vftable';
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 1) = v3;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  *((_QWORD *)v3 + 16) = 0;
  *((_QWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 18) = 0;
  *((_DWORD *)v3 + 18) = 0;
  *(_OWORD *)(v3 + 152) = 0;
  v3[168] = 0;
  *((_WORD *)v3 + 85) = -1;
  *((_QWORD *)v3 + 22) = 0;
  *((_QWORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 31) = 0;
  *(_DWORD *)(v3 + 42) = 0;
  *((_WORD *)v3 + 23) = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 60) = 0;
  *((_DWORD *)v3 + 6) = 38123070;
  *((_DWORD *)v3 + 7) = 180480;
  *((_QWORD *)v3 + 4) = "DesktopStickerEditorLaunchTest";
  *((_WORD *)v3 + 20) = 1;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  *((_QWORD *)v3 + 33) = 0;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::`vftable';
  *((_QWORD *)v3 + 32) = v3 + 16;
  result = a1;
  *((_QWORD *)v3 + 34) = 0;
  *((_QWORD *)v3 + 35) = 0;
  *((_QWORD *)v3 + 36) = 0;
  *((_QWORD *)v3 + 37) = 0;
  *((_QWORD *)v3 + 38) = 0;
  *((_QWORD *)v3 + 39) = 0;
  *((_QWORD *)v3 + 40) = 0;
  *((_QWORD *)v3 + 41) = 0;
  *((_DWORD *)v3 + 84) = 1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18002f574  mov     [rsp+arg_0], rbx
0x18002f579  mov     [rsp+arg_8], rsi
0x18002f57e  push    rdi
0x18002f57f  sub     rsp, 20h
0x18002f583  mov     rdi, rcx
0x18002f586  mov     ecx, 158h; cb
0x18002f58b  call    cs:__imp_CoTaskMemAlloc
0x18002f592  nop     dword ptr [rax+rax+00h]
0x18002f597  xor     esi, esi
0x18002f599  mov     rbx, rax
0x18002f59c  test    rax, rax
0x18002f59f  jz      loc_18002F6E1
0x18002f5a5  xor     r8d, r8d
0x18002f5a8  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18002f5af  mov     [rbx], rax
0x18002f5b2  lea     rdx, aDesktopsticker; "DesktopStickerEditorLaunchTest"
0x18002f5b9  mov     [rbx+10h], rsi
0x18002f5bd  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x18002f5c4  mov     [rbx+8], rbx
0x18002f5c8  xorps   xmm0, xmm0
0x18002f5cb  mov     [rbx+50h], rsi
0x18002f5cf  mov     [rbx+58h], rsi
0x18002f5d3  mov     [rbx+60h], rsi
0x18002f5d7  mov     [rbx+68h], rsi
0x18002f5db  mov     [rbx+70h], rsi
0x18002f5df  mov     [rbx+78h], rsi
0x18002f5e3  mov     [rbx+80h], rsi
0x18002f5ea  mov     [rbx+88h], rsi
0x18002f5f1  mov     [rbx+90h], rsi
0x18002f5f8  mov     [rbx+48h], esi
0x18002f5fb  movups  xmmword ptr [rbx+98h], xmm0
0x18002f602  mov     [rbx+0A8h], sil
0x18002f609  mov     word ptr [rbx+0AAh], 0FFFFh
0x18002f612  mov     [rbx+0B0h], rsi
0x18002f619  mov     [rbx+0B8h], rsi
0x18002f620  mov     [rbx+0F8h], rsi
0x18002f627  mov     [rbx+2Ah], r8d
0x18002f62b  mov     [rbx+2Eh], r8w
0x18002f630  mov     [rbx+0C0h], esi
0x18002f636  mov     [rbx+0F0h], esi
0x18002f63c  mov     dword ptr [rbx+18h], 245B63Eh
0x18002f643  mov     dword ptr [rbx+1Ch], 2C100h
0x18002f64a  mov     [rbx+20h], rdx
0x18002f64e  mov     word ptr [rbx+28h], 1
0x18002f654  mov     [rbx+30h], rsi
0x18002f658  mov     [rbx+38h], rsi
0x18002f65c  mov     [rbx+40h], rsi
0x18002f660  call    cs:__imp_InitializeCriticalSection
0x18002f667  nop     dword ptr [rax+rax+00h]
0x18002f66c  mov     [rbx+108h], rsi
0x18002f673  lea     rax, ??_7?$merged_data@U_tip_DesktopStickerEditorLaunchTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_DesktopStickerEditorLaunchTest_attributes,tip2::test_data_basic>::`vftable'
0x18002f67a  mov     [rbx], rax
0x18002f67d  lea     rax, [rbx+10h]
0x18002f681  mov     [rbx+100h], rax
0x18002f688  mov     rax, rdi
0x18002f68b  mov     [rbx+110h], rsi
0x18002f692  mov     [rbx+118h], rsi
0x18002f699  mov     [rbx+120h], rsi
0x18002f6a0  mov     [rbx+128h], rsi
0x18002f6a7  mov     [rbx+130h], rsi
0x18002f6ae  mov     [rbx+138h], rsi
0x18002f6b5  mov     [rbx+140h], rsi
0x18002f6bc  mov     [rbx+148h], rsi
0x18002f6c3  mov     rsi, [rsp+28h+arg_8]
0x18002f6c8  mov     dword ptr [rbx+150h], 1
0x18002f6d2  mov     [rdi], rbx
0x18002f6d5  mov     rbx, [rsp+28h+arg_0]
0x18002f6da  add     rsp, 20h
0x18002f6de  pop     rdi
0x18002f6df  retn
0x18002f6e1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
