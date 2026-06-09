# __DllMainCRTStartup

- ea: `0x180026414`
- end: `0x180026660`
- name: `__DllMainCRTStartup`
- size: `588`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800263d0`

## callees

- `0x18002618c`
- `0x180026414`
- `0x180026779`
- `0x180026960`
- `0x180026d70`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx
  int v6; // eax

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_180033080 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      v6 = dword_180033084;
      if ( (_DWORD)fdwReason == 1 )
        v6 = 1;
      dword_180033084 = v6;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_180033084 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x180026414  mov     rax, rsp
0x180026417  mov     [rax+20h], rbx
0x18002641b  mov     [rax+18h], r8
0x18002641f  mov     [rax+10h], edx
0x180026422  mov     [rax+8], rcx
0x180026426  push    rsi
0x180026427  push    rdi
0x180026428  push    r14
0x18002642a  sub     rsp, 150h
0x180026431  mov     edi, edx
0x180026433  mov     r14, rcx
0x180026436  mov     esi, 1
0x18002643b  mov     ebx, esi
0x18002643d  mov     [rsp+168h+var_148], ebx
0x180026441  cmp     edx, esi
0x180026443  ja      short loc_18002644B
0x180026445  mov     cs:__native_dllmain_reason, edx
0x18002644b  test    edx, edx
0x18002644d  jnz     short loc_180026462
0x18002644f  cmp     cs:dword_180033080, edx
0x180026455  jnz     short loc_180026462
0x180026457  xor     ebx, ebx
0x180026459  mov     [rsp+168h+var_148], ebx
0x18002645d  jmp     loc_18002663C
0x180026462  lea     eax, [rdx-1]
0x180026465  cmp     eax, esi
0x180026467  ja      loc_1800264FD
0x18002646d  mov     r9, cs:_pRawDllMain
0x180026474  test    r9, r9
0x180026477  jz      short loc_1800264BB
0x180026479  mov     eax, cs:dword_180033084
0x18002647f  cmp     edx, esi
0x180026481  cmovz   eax, esi
0x180026484  mov     cs:dword_180033084, eax
0x18002648a  mov     r8, [rsp+168h+lpvReserved]
0x180026492  mov     rax, r9
0x180026495  call    cs:__guard_dispatch_icall_fptr
0x18002649b  mov     ebx, eax
0x18002649d  mov     [rsp+168h+var_148], eax
0x1800264a1  jmp     short loc_1800264BB
0x1800264a3  xor     ebx, ebx
0x1800264a5  mov     [rsp+168h+var_148], ebx
0x1800264a9  lea     esi, [rbx+1]
0x1800264ac  mov     edi, [rsp+168h+arg_8]
0x1800264b3  mov     r14, [rsp+168h+arg_0]
0x1800264bb  test    ebx, ebx
0x1800264bd  jz      loc_18002663C
0x1800264c3  mov     r8, [rsp+168h+lpvReserved]
0x1800264cb  mov     edx, edi
0x1800264cd  mov     rcx, r14
0x1800264d0  call    _CRT_INIT
0x1800264d5  mov     ebx, eax
0x1800264d7  mov     [rsp+168h+var_148], eax
0x1800264db  jmp     short loc_1800264F5
0x1800264dd  xor     ebx, ebx
0x1800264df  mov     [rsp+168h+var_148], ebx
0x1800264e3  lea     esi, [rbx+1]
0x1800264e6  mov     edi, [rsp+168h+arg_8]
0x1800264ed  mov     r14, [rsp+168h+arg_0]
0x1800264f5  test    ebx, ebx
0x1800264f7  jz      loc_18002663C
0x1800264fd  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x180026505  mov     edx, edi; fdwReason
0x180026507  mov     rcx, r14; hinstDLL
0x18002650a  call    DllMain
0x18002650f  mov     ebx, eax
0x180026511  mov     [rsp+168h+var_148], eax
0x180026515  jmp     short loc_18002652F
0x180026517  xor     ebx, ebx
0x180026519  mov     [rsp+168h+var_148], ebx
0x18002651d  lea     esi, [rbx+1]
0x180026520  mov     edi, [rsp+168h+arg_8]
0x180026527  mov     r14, [rsp+168h+arg_0]
0x18002652f  cmp     edi, esi
0x180026531  jnz     loc_1800265C1
0x180026537  test    ebx, ebx
0x180026539  jnz     loc_1800265C1
0x18002653f  xor     r8d, r8d; lpvReserved
0x180026542  xor     edx, edx; fdwReason
0x180026544  mov     rcx, r14; hinstDLL
0x180026547  call    DllMain
0x18002654c  jmp     short loc_180026566
0x18002654e  mov     esi, 1
0x180026553  mov     edi, [rsp+168h+arg_8]
0x18002655a  mov     r14, [rsp+168h+arg_0]
0x180026562  mov     ebx, [rsp+168h+var_148]
0x180026566  xor     r8d, r8d
0x180026569  xor     edx, edx
0x18002656b  mov     rcx, r14
0x18002656e  call    _CRT_INIT
0x180026573  jmp     short loc_18002658D
0x180026575  mov     esi, 1
0x18002657a  mov     edi, [rsp+168h+arg_8]
0x180026581  mov     r14, [rsp+168h+arg_0]
0x180026589  mov     ebx, [rsp+168h+var_148]
0x18002658d  mov     rax, cs:_pRawDllMain
0x180026594  test    rax, rax
0x180026597  jz      short loc_1800265C1
0x180026599  xor     r8d, r8d
0x18002659c  xor     edx, edx
0x18002659e  mov     rcx, r14
0x1800265a1  call    cs:__guard_dispatch_icall_fptr
0x1800265a7  jmp     short loc_1800265C1
0x1800265a9  mov     esi, 1
0x1800265ae  mov     edi, [rsp+168h+arg_8]
0x1800265b5  mov     r14, [rsp+168h+arg_0]
0x1800265bd  mov     ebx, [rsp+168h+var_148]
0x1800265c1  test    edi, edi
0x1800265c3  jz      short loc_1800265CA
0x1800265c5  cmp     edi, 3
0x1800265c8  jnz     short loc_18002663C
0x1800265ca  mov     r8, [rsp+168h+lpvReserved]
0x1800265d2  mov     edx, edi
0x1800265d4  mov     rcx, r14
0x1800265d7  call    _CRT_INIT
0x1800265dc  mov     ebx, eax
0x1800265de  mov     [rsp+168h+var_148], eax
0x1800265e2  jmp     short loc_1800265FC
0x1800265e4  xor     ebx, ebx
0x1800265e6  mov     [rsp+168h+var_148], ebx
0x1800265ea  lea     esi, [rbx+1]
0x1800265ed  mov     edi, [rsp+168h+arg_8]
0x1800265f4  mov     r14, [rsp+168h+arg_0]
0x1800265fc  mov     rax, cs:_pRawDllMain
0x180026603  test    rax, rax
0x180026606  jz      short loc_18002663C
0x180026608  cmp     cs:dword_180033084, 0
0x18002660f  jz      short loc_18002663C
0x180026611  mov     r8, [rsp+168h+lpvReserved]
0x180026619  mov     edx, edi
0x18002661b  mov     rcx, r14
0x18002661e  call    cs:__guard_dispatch_icall_fptr
0x180026624  mov     ebx, eax
0x180026626  mov     [rsp+168h+var_148], eax
0x18002662a  jmp     short loc_18002663C
0x18002662c  xor     ebx, ebx
0x18002662e  mov     [rsp+168h+var_148], ebx
0x180026632  lea     esi, [rbx+1]
0x180026635  mov     edi, [rsp+168h+arg_8]
0x18002663c  cmp     edi, esi
0x18002663e  ja      short loc_18002664A
0x180026640  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18002664a  mov     eax, ebx
0x18002664c  mov     rbx, [rsp+168h+arg_18]
0x180026654  add     rsp, 150h
0x18002665b  pop     r14
0x18002665d  pop     rdi
0x18002665e  pop     rsi
0x18002665f  retn
0x180026de3  push    rbp
0x180026de5  sub     rsp, 20h
0x180026de9  mov     rbp, rdx
0x180026dec  mov     [rbp+108h], rcx
0x180026df3  mov     rax, [rcx]
0x180026df6  mov     edx, [rax]
0x180026df8  mov     [rbp+0A4h], edx
0x180026dfe  mov     [rbp+0C8h], rcx
0x180026e05  mov     [rbp+28h], edx
0x180026e08  mov     eax, [rbp+28h]
0x180026e0b  cmp     eax, 0E06D7363h
0x180026e10  jnz     short loc_180026E26
0x180026e12  mov     rdx, [rbp+0C8h]
0x180026e19  mov     ecx, [rbp+28h]
0x180026e1c  call    _XcptFilter_0
0x180026e21  mov     [rbp+30h], eax
0x180026e24  jmp     short loc_180026E2D
0x180026e26  mov     dword ptr [rbp+30h], 0
0x180026e2d  mov     eax, [rbp+30h]
0x180026e30  add     rsp, 20h
0x180026e34  pop     rbp
0x180026e35  retn
0x180026e37  push    rbp
0x180026e39  sub     rsp, 20h
0x180026e3d  mov     rbp, rdx
0x180026e40  mov     [rbp+110h], rcx
0x180026e47  mov     rax, [rcx]
0x180026e4a  mov     edx, [rax]
0x180026e4c  mov     [rbp+0A8h], edx
0x180026e52  mov     [rbp+0D0h], rcx
0x180026e59  mov     [rbp+38h], edx
0x180026e5c  mov     eax, [rbp+38h]
0x180026e5f  cmp     eax, 0E06D7363h
0x180026e64  jnz     short loc_180026E7A
0x180026e66  mov     rdx, [rbp+0D0h]
0x180026e6d  mov     ecx, [rbp+38h]
0x180026e70  call    _XcptFilter_0
0x180026e75  mov     [rbp+40h], eax
0x180026e78  jmp     short loc_180026E81
0x180026e7a  mov     dword ptr [rbp+40h], 0
0x180026e81  mov     eax, [rbp+40h]
0x180026e84  add     rsp, 20h
0x180026e88  pop     rbp
0x180026e89  retn
0x180026e8b  push    rbp
0x180026e8d  sub     rsp, 20h
0x180026e91  mov     rbp, rdx
0x180026e94  mov     [rbp+118h], rcx
0x180026e9b  mov     rax, [rcx]
0x180026e9e  mov     edx, [rax]
0x180026ea0  mov     [rbp+0ACh], edx
0x180026ea6  mov     [rbp+0D8h], rcx
0x180026ead  mov     [rbp+48h], edx
0x180026eb0  mov     eax, [rbp+48h]
0x180026eb3  cmp     eax, 0E06D7363h
0x180026eb8  jnz     short loc_180026ECE
0x180026eba  mov     rdx, [rbp+0D8h]
0x180026ec1  mov     ecx, [rbp+48h]
0x180026ec4  call    _XcptFilter_0
0x180026ec9  mov     [rbp+50h], eax
0x180026ecc  jmp     short loc_180026ED5
0x180026ece  mov     dword ptr [rbp+50h], 0
0x180026ed5  mov     eax, [rbp+50h]
0x180026ed8  add     rsp, 20h
0x180026edc  pop     rbp
0x180026edd  retn
0x180026edf  push    rbp
0x180026ee1  sub     rsp, 20h
0x180026ee5  mov     rbp, rdx
0x180026ee8  mov     [rbp+120h], rcx
0x180026eef  mov     rax, [rcx]
0x180026ef2  mov     edx, [rax]
0x180026ef4  mov     [rbp+0B0h], edx
0x180026efa  mov     [rbp+0E0h], rcx
0x180026f01  mov     [rbp+58h], edx
0x180026f04  mov     eax, [rbp+58h]
0x180026f07  cmp     eax, 0E06D7363h
0x180026f0c  jnz     short loc_180026F22
0x180026f0e  mov     rdx, [rbp+0E0h]
0x180026f15  mov     ecx, [rbp+58h]
0x180026f18  call    _XcptFilter_0
0x180026f1d  mov     [rbp+60h], eax
0x180026f20  jmp     short loc_180026F29
0x180026f22  mov     dword ptr [rbp+60h], 0
0x180026f29  mov     eax, [rbp+60h]
0x180026f2c  add     rsp, 20h
0x180026f30  pop     rbp
0x180026f31  retn
0x180026f33  push    rbp
0x180026f35  sub     rsp, 20h
0x180026f39  mov     rbp, rdx
0x180026f3c  mov     [rbp+128h], rcx
0x180026f43  mov     rax, [rcx]
0x180026f46  mov     edx, [rax]
0x180026f48  mov     [rbp+0B4h], edx
0x180026f4e  mov     [rbp+0E8h], rcx
0x180026f55  mov     [rbp+68h], edx
0x180026f58  mov     eax, [rbp+68h]
0x180026f5b  cmp     eax, 0E06D7363h
0x180026f60  jnz     short loc_180026F76
0x180026f62  mov     rdx, [rbp+0E8h]
0x180026f69  mov     ecx, [rbp+68h]
0x180026f6c  call    _XcptFilter_0
0x180026f71  mov     [rbp+70h], eax
0x180026f74  jmp     short loc_180026F7D
0x180026f76  mov     dword ptr [rbp+70h], 0
0x180026f7d  mov     eax, [rbp+70h]
0x180026f80  add     rsp, 20h
0x180026f84  pop     rbp
0x180026f85  retn
0x180026f87  push    rbp
0x180026f89  sub     rsp, 20h
0x180026f8d  mov     rbp, rdx
0x180026f90  mov     [rbp+130h], rcx
0x180026f97  mov     rax, [rcx]
0x180026f9a  mov     edx, [rax]
0x180026f9c  mov     [rbp+0B8h], edx
0x180026fa2  mov     [rbp+0F0h], rcx
0x180026fa9  mov     [rbp+78h], edx
0x180026fac  mov     eax, [rbp+78h]
0x180026faf  cmp     eax, 0E06D7363h
0x180026fb4  jnz     short loc_180026FCD
0x180026fb6  mov     rdx, [rbp+0F0h]
0x180026fbd  mov     ecx, [rbp+78h]
0x180026fc0  call    _XcptFilter_0
0x180026fc5  mov     [rbp+80h], eax
0x180026fcb  jmp     short loc_180026FD7
0x180026fcd  mov     dword ptr [rbp+80h], 0
0x180026fd7  mov     eax, [rbp+80h]
0x180026fdd  add     rsp, 20h
0x180026fe1  pop     rbp
0x180026fe2  retn
0x180026fe4  push    rbp
0x180026fe6  sub     rsp, 20h
0x180026fea  mov     rbp, rdx
0x180026fed  mov     [rbp+138h], rcx
0x180026ff4  mov     rax, [rcx]
0x180026ff7  mov     edx, [rax]
0x180026ff9  mov     [rbp+0BCh], edx
0x180026fff  mov     [rbp+0F8h], rcx
0x180027006  mov     [rbp+88h], edx
0x18002700c  mov     eax, [rbp+88h]
0x180027012  cmp     eax, 0E06D7363h
0x180027017  jnz     short loc_180027033
0x180027019  mov     rdx, [rbp+0F8h]
0x180027020  mov     ecx, [rbp+88h]
0x180027026  call    _XcptFilter_0
0x18002702b  mov     [rbp+90h], eax
0x180027031  jmp     short loc_18002703D
0x180027033  mov     dword ptr [rbp+90h], 0
0x18002703d  mov     eax, [rbp+90h]
  ... truncated ...
```
