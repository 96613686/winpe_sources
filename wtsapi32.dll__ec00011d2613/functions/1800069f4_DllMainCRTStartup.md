# __DllMainCRTStartup

- ea: `0x1800069f4`
- end: `0x180006c00`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800069b0`

## callees

- `0x180006780`
- `0x1800069f4`
- `0x180006df7`
- `0x180008a20`
- `0x180015600`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // edi
  unsigned int v5; // ebx

  v3 = a2;
  v5 = 1;
  if ( (unsigned int)a2 <= 1 )
    _native_dllmain_reason = a2;
  if ( (_DWORD)a2 || dword_18001F300 )
  {
    if ( (unsigned int)(a2 - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)a2 == 1 )
        dword_18001F304 = 1;
      v5 = pRawDllMain(a1, a2, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(a1, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = WTSSetSessionInformationA(a1, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          WTSSetSessionInformationA(a1, 0, 0);
          CRT_INIT(a1, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(a1, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(a1, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_18001F304 )
              v5 = pRawDllMain(a1, v3, a3);
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
0x1800069f4  mov     [rsp+arg_10], r8
0x1800069f9  mov     [rsp+arg_8], edx
0x1800069fd  mov     [rsp+arg_0], rcx
0x180006a02  push    rbx
0x180006a03  push    rsi
0x180006a04  push    rdi
0x180006a05  sub     rsp, 0F0h
0x180006a0c  mov     edi, edx
0x180006a0e  mov     rsi, rcx
0x180006a11  mov     ebx, 1
0x180006a16  cmp     edx, ebx
0x180006a18  ja      short loc_180006A20
0x180006a1a  mov     cs:__native_dllmain_reason, edx
0x180006a20  test    edx, edx
0x180006a22  jnz     short loc_180006A37
0x180006a24  cmp     cs:dword_18001F300, edx
0x180006a2a  jnz     short loc_180006A37
0x180006a2c  xor     ebx, ebx
0x180006a2e  mov     [rsp+108h+var_E8], ebx
0x180006a32  jmp     loc_180006BE4
0x180006a37  lea     eax, [rdx-1]
0x180006a3a  cmp     eax, 1
0x180006a3d  ja      loc_180006AC4
0x180006a43  mov     rax, cs:_pRawDllMain
0x180006a4a  test    rax, rax
0x180006a4d  jz      short loc_180006A85
0x180006a4f  cmp     edx, 1
0x180006a52  jnz     short loc_180006A5A
0x180006a54  mov     cs:dword_18001F304, edx
0x180006a5a  mov     r8, [rsp+108h+arg_10]
0x180006a62  call    cs:__guard_dispatch_icall_fptr
0x180006a68  mov     ebx, eax
0x180006a6a  mov     [rsp+108h+var_E8], eax
0x180006a6e  jmp     short loc_180006A85
0x180006a70  xor     ebx, ebx
0x180006a72  mov     [rsp+108h+var_E8], ebx
0x180006a76  mov     edi, [rsp+108h+arg_8]
0x180006a7d  mov     rsi, [rsp+108h+arg_0]
0x180006a85  test    ebx, ebx
0x180006a87  jz      loc_180006BE4
0x180006a8d  mov     r8, [rsp+108h+arg_10]
0x180006a95  mov     edx, edi
0x180006a97  mov     rcx, rsi
0x180006a9a  call    _CRT_INIT
0x180006a9f  mov     ebx, eax
0x180006aa1  mov     [rsp+108h+var_E8], eax
0x180006aa5  jmp     short loc_180006ABC
0x180006aa7  xor     ebx, ebx
0x180006aa9  mov     [rsp+108h+var_E8], ebx
0x180006aad  mov     edi, [rsp+108h+arg_8]
0x180006ab4  mov     rsi, [rsp+108h+arg_0]
0x180006abc  test    ebx, ebx
0x180006abe  jz      loc_180006BE4
0x180006ac4  mov     r8, [rsp+108h+arg_10]
0x180006acc  mov     edx, edi
0x180006ace  mov     rcx, rsi
0x180006ad1  call    WTSSetSessionInformationA
0x180006ad6  mov     ebx, eax
0x180006ad8  mov     [rsp+108h+var_E8], eax
0x180006adc  jmp     short loc_180006AF3
0x180006ade  xor     ebx, ebx
0x180006ae0  mov     [rsp+108h+var_E8], ebx
0x180006ae4  mov     edi, [rsp+108h+arg_8]
0x180006aeb  mov     rsi, [rsp+108h+arg_0]
0x180006af3  cmp     edi, 1
0x180006af6  jnz     short loc_180006B6F
0x180006af8  test    ebx, ebx
0x180006afa  jnz     short loc_180006B6F
0x180006afc  xor     r8d, r8d
0x180006aff  xor     edx, edx
0x180006b01  mov     rcx, rsi
0x180006b04  call    WTSSetSessionInformationA
0x180006b09  jmp     short loc_180006B1E
0x180006b0b  mov     edi, [rsp+108h+arg_8]
0x180006b12  mov     rsi, [rsp+108h+arg_0]
0x180006b1a  mov     ebx, [rsp+108h+var_E8]
0x180006b1e  xor     r8d, r8d
0x180006b21  xor     edx, edx
0x180006b23  mov     rcx, rsi
0x180006b26  call    _CRT_INIT
0x180006b2b  jmp     short loc_180006B40
0x180006b2d  mov     edi, [rsp+108h+arg_8]
0x180006b34  mov     rsi, [rsp+108h+arg_0]
0x180006b3c  mov     ebx, [rsp+108h+var_E8]
0x180006b40  mov     rax, cs:_pRawDllMain
0x180006b47  test    rax, rax
0x180006b4a  jz      short loc_180006B6F
0x180006b4c  xor     r8d, r8d
0x180006b4f  xor     edx, edx
0x180006b51  mov     rcx, rsi
0x180006b54  call    cs:__guard_dispatch_icall_fptr
0x180006b5a  jmp     short loc_180006B6F
0x180006b5c  mov     edi, [rsp+108h+arg_8]
0x180006b63  mov     rsi, [rsp+108h+arg_0]
0x180006b6b  mov     ebx, [rsp+108h+var_E8]
0x180006b6f  test    edi, edi
0x180006b71  jz      short loc_180006B78
0x180006b73  cmp     edi, 3
0x180006b76  jnz     short loc_180006BE4
0x180006b78  mov     r8, [rsp+108h+arg_10]
0x180006b80  mov     edx, edi
0x180006b82  mov     rcx, rsi
0x180006b85  call    _CRT_INIT
0x180006b8a  mov     ebx, eax
0x180006b8c  mov     [rsp+108h+var_E8], eax
0x180006b90  jmp     short loc_180006BA7
0x180006b92  xor     ebx, ebx
0x180006b94  mov     [rsp+108h+var_E8], ebx
0x180006b98  mov     edi, [rsp+108h+arg_8]
0x180006b9f  mov     rsi, [rsp+108h+arg_0]
0x180006ba7  mov     rax, cs:_pRawDllMain
0x180006bae  test    rax, rax
0x180006bb1  jz      short loc_180006BE4
0x180006bb3  cmp     cs:dword_18001F304, 0
0x180006bba  jz      short loc_180006BE4
0x180006bbc  mov     r8, [rsp+108h+arg_10]
0x180006bc4  mov     edx, edi
0x180006bc6  mov     rcx, rsi
0x180006bc9  call    cs:__guard_dispatch_icall_fptr
0x180006bcf  mov     ebx, eax
0x180006bd1  mov     [rsp+108h+var_E8], eax
0x180006bd5  jmp     short loc_180006BE4
0x180006bd7  xor     ebx, ebx
0x180006bd9  mov     [rsp+108h+var_E8], ebx
0x180006bdd  mov     edi, [rsp+108h+arg_8]
0x180006be4  cmp     edi, 1
0x180006be7  ja      short loc_180006BF3
0x180006be9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180006bf3  mov     eax, ebx
0x180006bf5  add     rsp, 0F0h
0x180006bfc  pop     rdi
0x180006bfd  pop     rsi
0x180006bfe  pop     rbx
0x180006bff  retn
0x1800156d0  push    rbp
0x1800156d2  sub     rsp, 20h
0x1800156d6  mov     rbp, rdx
0x1800156d9  mov     rax, [rcx]
0x1800156dc  mov     edx, [rax]
0x1800156de  mov     [rbp+0A8h], rcx
0x1800156e5  mov     [rbp+28h], edx
0x1800156e8  mov     eax, [rbp+28h]
0x1800156eb  cmp     eax, 0E06D7363h
0x1800156f0  jnz     short loc_180015706
0x1800156f2  mov     rdx, [rbp+0A8h]
0x1800156f9  mov     ecx, [rbp+28h]
0x1800156fc  call    _XcptFilter_0
0x180015701  mov     [rbp+30h], eax
0x180015704  jmp     short loc_18001570D
0x180015706  mov     dword ptr [rbp+30h], 0
0x18001570d  mov     eax, [rbp+30h]
0x180015710  add     rsp, 20h
0x180015714  pop     rbp
0x180015715  retn
0x180015717  push    rbp
0x180015719  sub     rsp, 20h
0x18001571d  mov     rbp, rdx
0x180015720  mov     rax, [rcx]
0x180015723  mov     edx, [rax]
0x180015725  mov     [rbp+0B0h], rcx
0x18001572c  mov     [rbp+38h], edx
0x18001572f  mov     eax, [rbp+38h]
0x180015732  cmp     eax, 0E06D7363h
0x180015737  jnz     short loc_18001574D
0x180015739  mov     rdx, [rbp+0B0h]
0x180015740  mov     ecx, [rbp+38h]
0x180015743  call    _XcptFilter_0
0x180015748  mov     [rbp+40h], eax
0x18001574b  jmp     short loc_180015754
0x18001574d  mov     dword ptr [rbp+40h], 0
0x180015754  mov     eax, [rbp+40h]
0x180015757  add     rsp, 20h
0x18001575b  pop     rbp
0x18001575c  retn
0x18001575e  push    rbp
0x180015760  sub     rsp, 20h
0x180015764  mov     rbp, rdx
0x180015767  mov     rax, [rcx]
0x18001576a  mov     edx, [rax]
0x18001576c  mov     [rbp+0B8h], rcx
0x180015773  mov     [rbp+48h], edx
0x180015776  mov     eax, [rbp+48h]
0x180015779  cmp     eax, 0E06D7363h
0x18001577e  jnz     short loc_180015794
0x180015780  mov     rdx, [rbp+0B8h]
0x180015787  mov     ecx, [rbp+48h]
0x18001578a  call    _XcptFilter_0
0x18001578f  mov     [rbp+50h], eax
0x180015792  jmp     short loc_18001579B
0x180015794  mov     dword ptr [rbp+50h], 0
0x18001579b  mov     eax, [rbp+50h]
0x18001579e  add     rsp, 20h
0x1800157a2  pop     rbp
0x1800157a3  retn
0x1800157a5  push    rbp
0x1800157a7  sub     rsp, 20h
0x1800157ab  mov     rbp, rdx
0x1800157ae  mov     rax, [rcx]
0x1800157b1  mov     edx, [rax]
0x1800157b3  mov     [rbp+0C0h], rcx
0x1800157ba  mov     [rbp+58h], edx
0x1800157bd  mov     eax, [rbp+58h]
0x1800157c0  cmp     eax, 0E06D7363h
0x1800157c5  jnz     short loc_1800157DB
0x1800157c7  mov     rdx, [rbp+0C0h]
0x1800157ce  mov     ecx, [rbp+58h]
0x1800157d1  call    _XcptFilter_0
0x1800157d6  mov     [rbp+60h], eax
0x1800157d9  jmp     short loc_1800157E2
0x1800157db  mov     dword ptr [rbp+60h], 0
0x1800157e2  mov     eax, [rbp+60h]
0x1800157e5  add     rsp, 20h
0x1800157e9  pop     rbp
0x1800157ea  retn
0x1800157ec  push    rbp
0x1800157ee  sub     rsp, 20h
0x1800157f2  mov     rbp, rdx
0x1800157f5  mov     rax, [rcx]
0x1800157f8  mov     edx, [rax]
0x1800157fa  mov     [rbp+0C8h], rcx
0x180015801  mov     [rbp+68h], edx
0x180015804  mov     eax, [rbp+68h]
0x180015807  cmp     eax, 0E06D7363h
0x18001580c  jnz     short loc_180015822
0x18001580e  mov     rdx, [rbp+0C8h]
0x180015815  mov     ecx, [rbp+68h]
0x180015818  call    _XcptFilter_0
0x18001581d  mov     [rbp+70h], eax
0x180015820  jmp     short loc_180015829
0x180015822  mov     dword ptr [rbp+70h], 0
0x180015829  mov     eax, [rbp+70h]
0x18001582c  add     rsp, 20h
0x180015830  pop     rbp
0x180015831  retn
0x180015833  push    rbp
0x180015835  sub     rsp, 20h
0x180015839  mov     rbp, rdx
0x18001583c  mov     rax, [rcx]
0x18001583f  mov     edx, [rax]
0x180015841  mov     [rbp+0D0h], rcx
0x180015848  mov     [rbp+78h], edx
0x18001584b  mov     eax, [rbp+78h]
0x18001584e  cmp     eax, 0E06D7363h
0x180015853  jnz     short loc_18001586C
0x180015855  mov     rdx, [rbp+0D0h]
0x18001585c  mov     ecx, [rbp+78h]
0x18001585f  call    _XcptFilter_0
0x180015864  mov     [rbp+80h], eax
0x18001586a  jmp     short loc_180015876
0x18001586c  mov     dword ptr [rbp+80h], 0
0x180015876  mov     eax, [rbp+80h]
0x18001587c  add     rsp, 20h
0x180015880  pop     rbp
0x180015881  retn
0x180015883  push    rbp
0x180015885  sub     rsp, 20h
0x180015889  mov     rbp, rdx
0x18001588c  mov     rax, [rcx]
0x18001588f  mov     edx, [rax]
0x180015891  mov     [rbp+0D8h], rcx
0x180015898  mov     [rbp+88h], edx
0x18001589e  mov     eax, [rbp+88h]
0x1800158a4  cmp     eax, 0E06D7363h
0x1800158a9  jnz     short loc_1800158C5
0x1800158ab  mov     rdx, [rbp+0D8h]
0x1800158b2  mov     ecx, [rbp+88h]
0x1800158b8  call    _XcptFilter_0
0x1800158bd  mov     [rbp+90h], eax
0x1800158c3  jmp     short loc_1800158CF
0x1800158c5  mov     dword ptr [rbp+90h], 0
0x1800158cf  mov     eax, [rbp+90h]
0x1800158d5  add     rsp, 20h
0x1800158d9  pop     rbp
0x1800158da  retn
0x1800158dc  push    rbp
0x1800158de  sub     rsp, 20h
0x1800158e2  mov     rbp, rdx
0x1800158e5  mov     rax, [rcx]
0x1800158e8  mov     edx, [rax]
0x1800158ea  mov     [rbp+0E0h], rcx
0x1800158f1  mov     [rbp+98h], edx
0x1800158f7  mov     eax, [rbp+98h]
0x1800158fd  cmp     eax, 0E06D7363h
0x180015902  jnz     short loc_18001591E
0x180015904  mov     rdx, [rbp+0E0h]
0x18001590b  mov     ecx, [rbp+98h]
0x180015911  call    _XcptFilter_0
0x180015916  mov     [rbp+0A0h], eax
0x18001591c  jmp     short loc_180015928
0x18001591e  mov     dword ptr [rbp+0A0h], 0
0x180015928  mov     eax, [rbp+0A0h]
0x18001592e  add     rsp, 20h
0x180015932  pop     rbp
0x180015933  retn
0x180015935  push    rbp
0x180015937  sub     rsp, 20h
0x18001593b  mov     rbp, rdx
0x18001593e  cmp     dword ptr [rbp+118h], 1
0x180015945  ja      short loc_180015951
0x180015947  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
