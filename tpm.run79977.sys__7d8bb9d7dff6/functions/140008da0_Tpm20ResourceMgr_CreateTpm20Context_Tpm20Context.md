# Tpm20ResourceMgr::CreateTpm20Context(Tpm20Context * *)

- ea: `0x140008da0`
- end: `0x140008f65`
- name: `?CreateTpm20Context@Tpm20ResourceMgr@@SAJPEAPEAVTpm20Context@@@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct Tpm20Context **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140008a5c`
- `0x140013bf0`

## callees

- `0x1400078b8`
- `0x140008da0`
- `0x140008f6c`
- `0x1400091e4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140008dc7`
- `ntoskrnl!ExAllocatePool2` at `0x140008e4b`
- `ntoskrnl!ExAllocatePool2` at `0x140008dc7`
- `ntoskrnl!ExAllocatePool2` at `0x140008e4b`

## pseudocode

```c
__int64 __fastcall Tpm20ResourceMgr::CreateTpm20Context(struct Tpm20Context **a1)
{
  _QWORD *Pool2; // rax
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  unsigned int v5; // edx
  _QWORD *v6; // r9
  unsigned int v7; // edi
  _UNKNOWN *retaddr; // [rsp+28h] [rbp+0h]

  Pool2 = (_QWORD *)ExAllocatePool2(257, 96, 1349349460);
  v3 = Pool2;
  if ( Pool2 )
  {
    v3 = Pool2 + 2;
    *Pool2 = retaddr;
    Pool2[1] = retaddr;
  }
  if ( v3 )
  {
    *((_WORD *)v3 + 31) = 0;
    v3[8] = 0;
    *((_BYTE *)v3 + 61) = 0;
    v3[9] = 0;
    v3[3] = v3 + 2;
    v3[2] = v3 + 2;
    v3[1] = v3;
    *v3 = v3;
    v3[5] = v3 + 4;
    v3[4] = v3 + 4;
    *((_DWORD *)v3 + 13) = 1073741832;
    *((_DWORD *)v3 + 12) = 1073741832;
    *((_BYTE *)v3 + 60) = 1;
    *((_DWORD *)v3 + 14) = 0;
    v4 = (_QWORD *)ExAllocatePool2(65, 64, 1349349460);
    v6 = v4;
    if ( v4 )
    {
      v6 = v4 + 2;
      *v4 = retaddr;
      v4[1] = retaddr;
    }
    if ( v6 )
    {
      v6[3] = 0;
      v6[4] = 0;
      v7 = 0;
      *(_WORD *)((char *)v6 + 45) = 0;
      *((_BYTE *)v6 + 47) = 0;
      *((_BYTE *)v6 + 44) = 0;
      *v6 = v3;
      *((_DWORD *)v6 + 10) = 0xFFFFFF;
      v6[2] = v6 + 1;
      v6[1] = v6 + 1;
      *a1 = (struct Tpm20Context *)v6;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids, v6);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
      v7 = -1073741670;
      Tpm20Resource::`scalar deleting destructor'((Tpm20Resource *)v3, v5);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids);
    return (unsigned int)-1073741670;
  }
  return v7;
}

```

## disassembly

```asm
0x140008da0  mov     [rsp+arg_0], rbx
0x140008da5  mov     [rsp+arg_8], rsi
0x140008daa  push    rdi
0x140008dab  sub     rsp, 20h
0x140008daf  mov     rdi, [rsp+28h]
0x140008db4  mov     rsi, rcx
0x140008db7  mov     ecx, 101h
0x140008dbc  mov     edx, 60h ; '`'
0x140008dc1  mov     r8d, 506D7054h
0x140008dc7  call    cs:__imp_ExAllocatePool2
0x140008dce  nop     dword ptr [rax+rax+00h]
0x140008dd3  mov     rbx, rax
0x140008dd6  test    rax, rax
0x140008dd9  jz      short loc_140008DEB
0x140008ddb  mov     rcx, [rsp+28h]
0x140008de0  add     rbx, 10h
0x140008de4  mov     [rax], rdi
0x140008de7  mov     [rax+8], rcx
0x140008deb  test    rbx, rbx
0x140008dee  jz      loc_140008F2C
0x140008df4  mov     rdi, [rsp+28h]
0x140008df9  xor     eax, eax
0x140008dfb  mov     [rbx+3Eh], ax
0x140008dff  mov     edx, 40h ; '@'
0x140008e04  mov     [rbx+40h], rax
0x140008e08  mov     r8d, 506D7054h
0x140008e0e  mov     [rbx+3Dh], al
0x140008e11  mov     [rbx+48h], rax
0x140008e15  lea     rax, [rbx+10h]
0x140008e19  mov     [rax+8], rax
0x140008e1d  lea     ecx, [rdx+1]
0x140008e20  mov     [rax], rax
0x140008e23  lea     rax, [rbx+20h]
0x140008e27  mov     [rbx+8], rbx
0x140008e2b  mov     [rbx], rbx
0x140008e2e  mov     [rax+8], rax
0x140008e32  mov     [rax], rax
0x140008e35  mov     eax, 40000008h
0x140008e3a  mov     [rbx+34h], eax
0x140008e3d  mov     [rbx+30h], eax
0x140008e40  mov     byte ptr [rbx+3Ch], 1
0x140008e44  mov     dword ptr [rbx+38h], 0
0x140008e4b  call    cs:__imp_ExAllocatePool2
0x140008e52  nop     dword ptr [rax+rax+00h]
0x140008e57  mov     r9, rax
0x140008e5a  test    rax, rax
0x140008e5d  jz      short loc_140008E6F
0x140008e5f  mov     rcx, [rsp+28h]
0x140008e64  add     r9, 10h
0x140008e68  mov     [rax], rdi
0x140008e6b  mov     [rax+8], rcx
0x140008e6f  test    r9, r9
0x140008e72  jz      short loc_140008EEE
0x140008e74  mov     qword ptr [r9+18h], 0
0x140008e7c  xor     eax, eax
0x140008e7e  mov     qword ptr [r9+20h], 0
0x140008e86  xor     edi, edi
0x140008e88  mov     [r9+2Dh], ax
0x140008e8d  mov     [r9+2Fh], al
0x140008e91  mov     [r9+2Ch], al
0x140008e95  lea     rax, [r9+8]
0x140008e99  mov     [r9], rbx
0x140008e9c  mov     dword ptr [r9+28h], 0FFFFFFh
0x140008ea4  mov     [rax+8], rax
0x140008ea8  mov     [rax], rax
0x140008eab  mov     [rsi], r9
0x140008eae  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008eb5  lea     rax, WPP_GLOBAL_Control
0x140008ebc  cmp     rcx, rax
0x140008ebf  jz      short loc_140008EDB
0x140008ec1  mov     eax, [rcx+2Ch]
0x140008ec4  test    al, 4
0x140008ec6  jz      short loc_140008EDB
0x140008ec8  mov     rcx, [rcx+18h]
0x140008ecc  lea     edx, [rdi+12h]
0x140008ecf  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008ed6  call    WPP_SF_q
0x140008edb  mov     rbx, [rsp+28h+arg_0]
0x140008ee0  mov     eax, edi
0x140008ee2  mov     rsi, [rsp+28h+arg_8]
0x140008ee7  add     rsp, 20h
0x140008eeb  pop     rdi
0x140008eec  retn
0x140008eee  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008ef5  lea     rax, WPP_GLOBAL_Control
0x140008efc  cmp     rcx, rax
0x140008eff  jz      short loc_140008F1D
0x140008f01  mov     eax, [rcx+2Ch]
0x140008f04  test    al, 1
0x140008f06  jz      short loc_140008F1D
0x140008f08  mov     rcx, [rcx+18h]
0x140008f0c  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008f13  mov     edx, 11h
0x140008f18  call    WPP_SF_
0x140008f1d  mov     rcx, rbx; this
0x140008f20  mov     edi, 0C000009Ah
0x140008f25  call    ??_GTpm20Resource@@AEAAPEAXI@Z; Tpm20Resource::`scalar deleting destructor'(uint)
0x140008f2a  jmp     short loc_140008EDB
0x140008f2c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008f33  lea     rax, WPP_GLOBAL_Control
0x140008f3a  cmp     rcx, rax
0x140008f3d  jz      short loc_140008F5B
0x140008f3f  mov     eax, [rcx+2Ch]
0x140008f42  test    al, 1
0x140008f44  jz      short loc_140008F5B
0x140008f46  mov     rcx, [rcx+18h]
0x140008f4a  lea     r8, WPP_8e0463bd2bbe316f38665ed291c614ef_Traceguids
0x140008f51  mov     edx, 10h
0x140008f56  call    WPP_SF_
0x140008f5b  mov     edi, 0C000009Ah
0x140008f60  jmp     loc_140008EDB
```
