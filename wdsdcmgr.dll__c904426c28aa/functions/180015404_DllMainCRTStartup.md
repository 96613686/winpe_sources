# __DllMainCRTStartup

- ea: `0x180015404`
- end: `0x180015650`
- name: `__DllMainCRTStartup`
- size: `588`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800153c0`

## callees

- `0x180008780`
- `0x18001517c`
- `0x180015404`
- `0x1800159b4`
- `0x180015cc0`

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
  if ( (_DWORD)fdwReason || dword_18001D780 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      v6 = dword_18001D784;
      if ( (_DWORD)fdwReason == 1 )
        v6 = 1;
      dword_18001D784 = v6;
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
            if ( dword_18001D784 )
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
0x180015404  mov     rax, rsp
0x180015407  mov     [rax+20h], rbx
0x18001540b  mov     [rax+18h], r8
0x18001540f  mov     [rax+10h], edx
0x180015412  mov     [rax+8], rcx
0x180015416  push    rsi
0x180015417  push    rdi
0x180015418  push    r14
0x18001541a  sub     rsp, 150h
0x180015421  mov     edi, edx
0x180015423  mov     r14, rcx
0x180015426  mov     esi, 1
0x18001542b  mov     ebx, esi
0x18001542d  mov     [rsp+168h+var_148], ebx
0x180015431  cmp     edx, esi
0x180015433  ja      short loc_18001543B
0x180015435  mov     cs:__native_dllmain_reason, edx
0x18001543b  test    edx, edx
0x18001543d  jnz     short loc_180015452
0x18001543f  cmp     cs:dword_18001D780, edx
0x180015445  jnz     short loc_180015452
0x180015447  xor     ebx, ebx
0x180015449  mov     [rsp+168h+var_148], ebx
0x18001544d  jmp     loc_18001562C
0x180015452  lea     eax, [rdx-1]
0x180015455  cmp     eax, esi
0x180015457  ja      loc_1800154ED
0x18001545d  mov     r9, cs:_pRawDllMain
0x180015464  test    r9, r9
0x180015467  jz      short loc_1800154AB
0x180015469  mov     eax, cs:dword_18001D784
0x18001546f  cmp     edx, esi
0x180015471  cmovz   eax, esi
0x180015474  mov     cs:dword_18001D784, eax
0x18001547a  mov     r8, [rsp+168h+lpvReserved]
0x180015482  mov     rax, r9
0x180015485  call    cs:__guard_dispatch_icall_fptr
0x18001548b  mov     ebx, eax
0x18001548d  mov     [rsp+168h+var_148], eax
0x180015491  jmp     short loc_1800154AB
0x180015493  xor     ebx, ebx
0x180015495  mov     [rsp+168h+var_148], ebx
0x180015499  lea     esi, [rbx+1]
0x18001549c  mov     edi, [rsp+168h+arg_8]
0x1800154a3  mov     r14, [rsp+168h+arg_0]
0x1800154ab  test    ebx, ebx
0x1800154ad  jz      loc_18001562C
0x1800154b3  mov     r8, [rsp+168h+lpvReserved]
0x1800154bb  mov     edx, edi
0x1800154bd  mov     rcx, r14
0x1800154c0  call    _CRT_INIT
0x1800154c5  mov     ebx, eax
0x1800154c7  mov     [rsp+168h+var_148], eax
0x1800154cb  jmp     short loc_1800154E5
0x1800154cd  xor     ebx, ebx
0x1800154cf  mov     [rsp+168h+var_148], ebx
0x1800154d3  lea     esi, [rbx+1]
0x1800154d6  mov     edi, [rsp+168h+arg_8]
0x1800154dd  mov     r14, [rsp+168h+arg_0]
0x1800154e5  test    ebx, ebx
0x1800154e7  jz      loc_18001562C
0x1800154ed  mov     r8, [rsp+168h+lpvReserved]; lpvReserved
0x1800154f5  mov     edx, edi; fdwReason
0x1800154f7  mov     rcx, r14; hinstDLL
0x1800154fa  call    DllMain
0x1800154ff  mov     ebx, eax
0x180015501  mov     [rsp+168h+var_148], eax
0x180015505  jmp     short loc_18001551F
0x180015507  xor     ebx, ebx
0x180015509  mov     [rsp+168h+var_148], ebx
0x18001550d  lea     esi, [rbx+1]
0x180015510  mov     edi, [rsp+168h+arg_8]
0x180015517  mov     r14, [rsp+168h+arg_0]
0x18001551f  cmp     edi, esi
0x180015521  jnz     loc_1800155B1
0x180015527  test    ebx, ebx
0x180015529  jnz     loc_1800155B1
0x18001552f  xor     r8d, r8d; lpvReserved
0x180015532  xor     edx, edx; fdwReason
0x180015534  mov     rcx, r14; hinstDLL
0x180015537  call    DllMain
0x18001553c  jmp     short loc_180015556
0x18001553e  mov     esi, 1
0x180015543  mov     edi, [rsp+168h+arg_8]
0x18001554a  mov     r14, [rsp+168h+arg_0]
0x180015552  mov     ebx, [rsp+168h+var_148]
0x180015556  xor     r8d, r8d
0x180015559  xor     edx, edx
0x18001555b  mov     rcx, r14
0x18001555e  call    _CRT_INIT
0x180015563  jmp     short loc_18001557D
0x180015565  mov     esi, 1
0x18001556a  mov     edi, [rsp+168h+arg_8]
0x180015571  mov     r14, [rsp+168h+arg_0]
0x180015579  mov     ebx, [rsp+168h+var_148]
0x18001557d  mov     rax, cs:_pRawDllMain
0x180015584  test    rax, rax
0x180015587  jz      short loc_1800155B1
0x180015589  xor     r8d, r8d
0x18001558c  xor     edx, edx
0x18001558e  mov     rcx, r14
0x180015591  call    cs:__guard_dispatch_icall_fptr
0x180015597  jmp     short loc_1800155B1
0x180015599  mov     esi, 1
0x18001559e  mov     edi, [rsp+168h+arg_8]
0x1800155a5  mov     r14, [rsp+168h+arg_0]
0x1800155ad  mov     ebx, [rsp+168h+var_148]
0x1800155b1  test    edi, edi
0x1800155b3  jz      short loc_1800155BA
0x1800155b5  cmp     edi, 3
0x1800155b8  jnz     short loc_18001562C
0x1800155ba  mov     r8, [rsp+168h+lpvReserved]
0x1800155c2  mov     edx, edi
0x1800155c4  mov     rcx, r14
0x1800155c7  call    _CRT_INIT
0x1800155cc  mov     ebx, eax
0x1800155ce  mov     [rsp+168h+var_148], eax
0x1800155d2  jmp     short loc_1800155EC
0x1800155d4  xor     ebx, ebx
0x1800155d6  mov     [rsp+168h+var_148], ebx
0x1800155da  lea     esi, [rbx+1]
0x1800155dd  mov     edi, [rsp+168h+arg_8]
0x1800155e4  mov     r14, [rsp+168h+arg_0]
0x1800155ec  mov     rax, cs:_pRawDllMain
0x1800155f3  test    rax, rax
0x1800155f6  jz      short loc_18001562C
0x1800155f8  cmp     cs:dword_18001D784, 0
0x1800155ff  jz      short loc_18001562C
0x180015601  mov     r8, [rsp+168h+lpvReserved]
0x180015609  mov     edx, edi
0x18001560b  mov     rcx, r14
0x18001560e  call    cs:__guard_dispatch_icall_fptr
0x180015614  mov     ebx, eax
0x180015616  mov     [rsp+168h+var_148], eax
0x18001561a  jmp     short loc_18001562C
0x18001561c  xor     ebx, ebx
0x18001561e  mov     [rsp+168h+var_148], ebx
0x180015622  lea     esi, [rbx+1]
0x180015625  mov     edi, [rsp+168h+arg_8]
0x18001562c  cmp     edi, esi
0x18001562e  ja      short loc_18001563A
0x180015630  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18001563a  mov     eax, ebx
0x18001563c  mov     rbx, [rsp+168h+arg_18]
0x180015644  add     rsp, 150h
0x18001564b  pop     r14
0x18001564d  pop     rdi
0x18001564e  pop     rsi
0x18001564f  retn
0x180015cf6  push    rbp
0x180015cf8  sub     rsp, 20h
0x180015cfc  mov     rbp, rdx
0x180015cff  mov     [rbp+108h], rcx
0x180015d06  mov     rax, [rcx]
0x180015d09  mov     edx, [rax]
0x180015d0b  mov     [rbp+0A4h], edx
0x180015d11  mov     [rbp+0C8h], rcx
0x180015d18  mov     [rbp+28h], edx
0x180015d1b  mov     eax, [rbp+28h]
0x180015d1e  cmp     eax, 0E06D7363h
0x180015d23  jnz     short loc_180015D39
0x180015d25  mov     rdx, [rbp+0C8h]
0x180015d2c  mov     ecx, [rbp+28h]
0x180015d2f  call    _XcptFilter_0
0x180015d34  mov     [rbp+30h], eax
0x180015d37  jmp     short loc_180015D40
0x180015d39  mov     dword ptr [rbp+30h], 0
0x180015d40  mov     eax, [rbp+30h]
0x180015d43  add     rsp, 20h
0x180015d47  pop     rbp
0x180015d48  retn
0x180015d4a  push    rbp
0x180015d4c  sub     rsp, 20h
0x180015d50  mov     rbp, rdx
0x180015d53  mov     [rbp+110h], rcx
0x180015d5a  mov     rax, [rcx]
0x180015d5d  mov     edx, [rax]
0x180015d5f  mov     [rbp+0A8h], edx
0x180015d65  mov     [rbp+0D0h], rcx
0x180015d6c  mov     [rbp+38h], edx
0x180015d6f  mov     eax, [rbp+38h]
0x180015d72  cmp     eax, 0E06D7363h
0x180015d77  jnz     short loc_180015D8D
0x180015d79  mov     rdx, [rbp+0D0h]
0x180015d80  mov     ecx, [rbp+38h]
0x180015d83  call    _XcptFilter_0
0x180015d88  mov     [rbp+40h], eax
0x180015d8b  jmp     short loc_180015D94
0x180015d8d  mov     dword ptr [rbp+40h], 0
0x180015d94  mov     eax, [rbp+40h]
0x180015d97  add     rsp, 20h
0x180015d9b  pop     rbp
0x180015d9c  retn
0x180015d9e  push    rbp
0x180015da0  sub     rsp, 20h
0x180015da4  mov     rbp, rdx
0x180015da7  mov     [rbp+118h], rcx
0x180015dae  mov     rax, [rcx]
0x180015db1  mov     edx, [rax]
0x180015db3  mov     [rbp+0ACh], edx
0x180015db9  mov     [rbp+0D8h], rcx
0x180015dc0  mov     [rbp+48h], edx
0x180015dc3  mov     eax, [rbp+48h]
0x180015dc6  cmp     eax, 0E06D7363h
0x180015dcb  jnz     short loc_180015DE1
0x180015dcd  mov     rdx, [rbp+0D8h]
0x180015dd4  mov     ecx, [rbp+48h]
0x180015dd7  call    _XcptFilter_0
0x180015ddc  mov     [rbp+50h], eax
0x180015ddf  jmp     short loc_180015DE8
0x180015de1  mov     dword ptr [rbp+50h], 0
0x180015de8  mov     eax, [rbp+50h]
0x180015deb  add     rsp, 20h
0x180015def  pop     rbp
0x180015df0  retn
0x180015df2  push    rbp
0x180015df4  sub     rsp, 20h
0x180015df8  mov     rbp, rdx
0x180015dfb  mov     [rbp+120h], rcx
0x180015e02  mov     rax, [rcx]
0x180015e05  mov     edx, [rax]
0x180015e07  mov     [rbp+0B0h], edx
0x180015e0d  mov     [rbp+0E0h], rcx
0x180015e14  mov     [rbp+58h], edx
0x180015e17  mov     eax, [rbp+58h]
0x180015e1a  cmp     eax, 0E06D7363h
0x180015e1f  jnz     short loc_180015E35
0x180015e21  mov     rdx, [rbp+0E0h]
0x180015e28  mov     ecx, [rbp+58h]
0x180015e2b  call    _XcptFilter_0
0x180015e30  mov     [rbp+60h], eax
0x180015e33  jmp     short loc_180015E3C
0x180015e35  mov     dword ptr [rbp+60h], 0
0x180015e3c  mov     eax, [rbp+60h]
0x180015e3f  add     rsp, 20h
0x180015e43  pop     rbp
0x180015e44  retn
0x180015e46  push    rbp
0x180015e48  sub     rsp, 20h
0x180015e4c  mov     rbp, rdx
0x180015e4f  mov     [rbp+128h], rcx
0x180015e56  mov     rax, [rcx]
0x180015e59  mov     edx, [rax]
0x180015e5b  mov     [rbp+0B4h], edx
0x180015e61  mov     [rbp+0E8h], rcx
0x180015e68  mov     [rbp+68h], edx
0x180015e6b  mov     eax, [rbp+68h]
0x180015e6e  cmp     eax, 0E06D7363h
0x180015e73  jnz     short loc_180015E89
0x180015e75  mov     rdx, [rbp+0E8h]
0x180015e7c  mov     ecx, [rbp+68h]
0x180015e7f  call    _XcptFilter_0
0x180015e84  mov     [rbp+70h], eax
0x180015e87  jmp     short loc_180015E90
0x180015e89  mov     dword ptr [rbp+70h], 0
0x180015e90  mov     eax, [rbp+70h]
0x180015e93  add     rsp, 20h
0x180015e97  pop     rbp
0x180015e98  retn
0x180015e9a  push    rbp
0x180015e9c  sub     rsp, 20h
0x180015ea0  mov     rbp, rdx
0x180015ea3  mov     [rbp+130h], rcx
0x180015eaa  mov     rax, [rcx]
0x180015ead  mov     edx, [rax]
0x180015eaf  mov     [rbp+0B8h], edx
0x180015eb5  mov     [rbp+0F0h], rcx
0x180015ebc  mov     [rbp+78h], edx
0x180015ebf  mov     eax, [rbp+78h]
0x180015ec2  cmp     eax, 0E06D7363h
0x180015ec7  jnz     short loc_180015EE0
0x180015ec9  mov     rdx, [rbp+0F0h]
0x180015ed0  mov     ecx, [rbp+78h]
0x180015ed3  call    _XcptFilter_0
0x180015ed8  mov     [rbp+80h], eax
0x180015ede  jmp     short loc_180015EEA
0x180015ee0  mov     dword ptr [rbp+80h], 0
0x180015eea  mov     eax, [rbp+80h]
0x180015ef0  add     rsp, 20h
0x180015ef4  pop     rbp
0x180015ef5  retn
0x180015ef7  push    rbp
0x180015ef9  sub     rsp, 20h
0x180015efd  mov     rbp, rdx
0x180015f00  mov     [rbp+138h], rcx
0x180015f07  mov     rax, [rcx]
0x180015f0a  mov     edx, [rax]
0x180015f0c  mov     [rbp+0BCh], edx
0x180015f12  mov     [rbp+0F8h], rcx
0x180015f19  mov     [rbp+88h], edx
0x180015f1f  mov     eax, [rbp+88h]
0x180015f25  cmp     eax, 0E06D7363h
0x180015f2a  jnz     short loc_180015F46
0x180015f2c  mov     rdx, [rbp+0F8h]
0x180015f33  mov     ecx, [rbp+88h]
0x180015f39  call    _XcptFilter_0
0x180015f3e  mov     [rbp+90h], eax
0x180015f44  jmp     short loc_180015F50
0x180015f46  mov     dword ptr [rbp+90h], 0
0x180015f50  mov     eax, [rbp+90h]
  ... truncated ...
```
