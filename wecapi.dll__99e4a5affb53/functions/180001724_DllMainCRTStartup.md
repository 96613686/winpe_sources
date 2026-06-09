# __DllMainCRTStartup

- ea: `0x180001724`
- end: `0x180001930`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800016e0`

## callees

- `0x1800014b0`
- `0x180001724`
- `0x180001af6`
- `0x1800044c0`
- `0x18000bad0`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_180014470 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180014474 = 1;
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
            if ( dword_180014474 )
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
0x180001724  mov     [rsp+lpvReserved], r8
0x180001729  mov     [rsp+arg_8], edx
0x18000172d  mov     [rsp+arg_0], rcx
0x180001732  push    rbx
0x180001733  push    rsi
0x180001734  push    rdi
0x180001735  sub     rsp, 0F0h
0x18000173c  mov     edi, edx
0x18000173e  mov     rsi, rcx
0x180001741  mov     ebx, 1
0x180001746  cmp     edx, ebx
0x180001748  ja      short loc_180001750
0x18000174a  mov     cs:__native_dllmain_reason, edx
0x180001750  test    edx, edx
0x180001752  jnz     short loc_180001767
0x180001754  cmp     cs:dword_180014470, edx
0x18000175a  jnz     short loc_180001767
0x18000175c  xor     ebx, ebx
0x18000175e  mov     [rsp+108h+var_E8], ebx
0x180001762  jmp     loc_180001914
0x180001767  lea     eax, [rdx-1]
0x18000176a  cmp     eax, 1
0x18000176d  ja      loc_1800017F4
0x180001773  mov     rax, cs:_pRawDllMain
0x18000177a  test    rax, rax
0x18000177d  jz      short loc_1800017B5
0x18000177f  cmp     edx, 1
0x180001782  jnz     short loc_18000178A
0x180001784  mov     cs:dword_180014474, edx
0x18000178a  mov     r8, [rsp+108h+lpvReserved]
0x180001792  call    cs:__guard_dispatch_icall_fptr
0x180001798  mov     ebx, eax
0x18000179a  mov     [rsp+108h+var_E8], eax
0x18000179e  jmp     short loc_1800017B5
0x1800017a0  xor     ebx, ebx
0x1800017a2  mov     [rsp+108h+var_E8], ebx
0x1800017a6  mov     edi, [rsp+108h+arg_8]
0x1800017ad  mov     rsi, [rsp+108h+arg_0]
0x1800017b5  test    ebx, ebx
0x1800017b7  jz      loc_180001914
0x1800017bd  mov     r8, [rsp+108h+lpvReserved]
0x1800017c5  mov     edx, edi
0x1800017c7  mov     rcx, rsi
0x1800017ca  call    _CRT_INIT
0x1800017cf  mov     ebx, eax
0x1800017d1  mov     [rsp+108h+var_E8], eax
0x1800017d5  jmp     short loc_1800017EC
0x1800017d7  xor     ebx, ebx
0x1800017d9  mov     [rsp+108h+var_E8], ebx
0x1800017dd  mov     edi, [rsp+108h+arg_8]
0x1800017e4  mov     rsi, [rsp+108h+arg_0]
0x1800017ec  test    ebx, ebx
0x1800017ee  jz      loc_180001914
0x1800017f4  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x1800017fc  mov     edx, edi; fdwReason
0x1800017fe  mov     rcx, rsi; hinstDLL
0x180001801  call    DllMain
0x180001806  mov     ebx, eax
0x180001808  mov     [rsp+108h+var_E8], eax
0x18000180c  jmp     short loc_180001823
0x18000180e  xor     ebx, ebx
0x180001810  mov     [rsp+108h+var_E8], ebx
0x180001814  mov     edi, [rsp+108h+arg_8]
0x18000181b  mov     rsi, [rsp+108h+arg_0]
0x180001823  cmp     edi, 1
0x180001826  jnz     short loc_18000189F
0x180001828  test    ebx, ebx
0x18000182a  jnz     short loc_18000189F
0x18000182c  xor     r8d, r8d; lpvReserved
0x18000182f  xor     edx, edx; fdwReason
0x180001831  mov     rcx, rsi; hinstDLL
0x180001834  call    DllMain
0x180001839  jmp     short loc_18000184E
0x18000183b  mov     edi, [rsp+108h+arg_8]
0x180001842  mov     rsi, [rsp+108h+arg_0]
0x18000184a  mov     ebx, [rsp+108h+var_E8]
0x18000184e  xor     r8d, r8d
0x180001851  xor     edx, edx
0x180001853  mov     rcx, rsi
0x180001856  call    _CRT_INIT
0x18000185b  jmp     short loc_180001870
0x18000185d  mov     edi, [rsp+108h+arg_8]
0x180001864  mov     rsi, [rsp+108h+arg_0]
0x18000186c  mov     ebx, [rsp+108h+var_E8]
0x180001870  mov     rax, cs:_pRawDllMain
0x180001877  test    rax, rax
0x18000187a  jz      short loc_18000189F
0x18000187c  xor     r8d, r8d
0x18000187f  xor     edx, edx
0x180001881  mov     rcx, rsi
0x180001884  call    cs:__guard_dispatch_icall_fptr
0x18000188a  jmp     short loc_18000189F
0x18000188c  mov     edi, [rsp+108h+arg_8]
0x180001893  mov     rsi, [rsp+108h+arg_0]
0x18000189b  mov     ebx, [rsp+108h+var_E8]
0x18000189f  test    edi, edi
0x1800018a1  jz      short loc_1800018A8
0x1800018a3  cmp     edi, 3
0x1800018a6  jnz     short loc_180001914
0x1800018a8  mov     r8, [rsp+108h+lpvReserved]
0x1800018b0  mov     edx, edi
0x1800018b2  mov     rcx, rsi
0x1800018b5  call    _CRT_INIT
0x1800018ba  mov     ebx, eax
0x1800018bc  mov     [rsp+108h+var_E8], eax
0x1800018c0  jmp     short loc_1800018D7
0x1800018c2  xor     ebx, ebx
0x1800018c4  mov     [rsp+108h+var_E8], ebx
0x1800018c8  mov     edi, [rsp+108h+arg_8]
0x1800018cf  mov     rsi, [rsp+108h+arg_0]
0x1800018d7  mov     rax, cs:_pRawDllMain
0x1800018de  test    rax, rax
0x1800018e1  jz      short loc_180001914
0x1800018e3  cmp     cs:dword_180014474, 0
0x1800018ea  jz      short loc_180001914
0x1800018ec  mov     r8, [rsp+108h+lpvReserved]
0x1800018f4  mov     edx, edi
0x1800018f6  mov     rcx, rsi
0x1800018f9  call    cs:__guard_dispatch_icall_fptr
0x1800018ff  mov     ebx, eax
0x180001901  mov     [rsp+108h+var_E8], eax
0x180001905  jmp     short loc_180001914
0x180001907  xor     ebx, ebx
0x180001909  mov     [rsp+108h+var_E8], ebx
0x18000190d  mov     edi, [rsp+108h+arg_8]
0x180001914  cmp     edi, 1
0x180001917  ja      short loc_180001923
0x180001919  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001923  mov     eax, ebx
0x180001925  add     rsp, 0F0h
0x18000192c  pop     rdi
0x18000192d  pop     rsi
0x18000192e  pop     rbx
0x18000192f  retn
0x18000bb10  push    rbp
0x18000bb12  sub     rsp, 20h
0x18000bb16  mov     rbp, rdx
0x18000bb19  mov     rax, [rcx]
0x18000bb1c  mov     edx, [rax]
0x18000bb1e  mov     [rbp+0A8h], rcx
0x18000bb25  mov     [rbp+28h], edx
0x18000bb28  mov     eax, [rbp+28h]
0x18000bb2b  cmp     eax, 0E06D7363h
0x18000bb30  jnz     short loc_18000BB46
0x18000bb32  mov     rdx, [rbp+0A8h]
0x18000bb39  mov     ecx, [rbp+28h]
0x18000bb3c  call    _XcptFilter_0
0x18000bb41  mov     [rbp+30h], eax
0x18000bb44  jmp     short loc_18000BB4D
0x18000bb46  mov     dword ptr [rbp+30h], 0
0x18000bb4d  mov     eax, [rbp+30h]
0x18000bb50  add     rsp, 20h
0x18000bb54  pop     rbp
0x18000bb55  retn
0x18000bb57  push    rbp
0x18000bb59  sub     rsp, 20h
0x18000bb5d  mov     rbp, rdx
0x18000bb60  mov     rax, [rcx]
0x18000bb63  mov     edx, [rax]
0x18000bb65  mov     [rbp+0B0h], rcx
0x18000bb6c  mov     [rbp+38h], edx
0x18000bb6f  mov     eax, [rbp+38h]
0x18000bb72  cmp     eax, 0E06D7363h
0x18000bb77  jnz     short loc_18000BB8D
0x18000bb79  mov     rdx, [rbp+0B0h]
0x18000bb80  mov     ecx, [rbp+38h]
0x18000bb83  call    _XcptFilter_0
0x18000bb88  mov     [rbp+40h], eax
0x18000bb8b  jmp     short loc_18000BB94
0x18000bb8d  mov     dword ptr [rbp+40h], 0
0x18000bb94  mov     eax, [rbp+40h]
0x18000bb97  add     rsp, 20h
0x18000bb9b  pop     rbp
0x18000bb9c  retn
0x18000bb9e  push    rbp
0x18000bba0  sub     rsp, 20h
0x18000bba4  mov     rbp, rdx
0x18000bba7  mov     rax, [rcx]
0x18000bbaa  mov     edx, [rax]
0x18000bbac  mov     [rbp+0B8h], rcx
0x18000bbb3  mov     [rbp+48h], edx
0x18000bbb6  mov     eax, [rbp+48h]
0x18000bbb9  cmp     eax, 0E06D7363h
0x18000bbbe  jnz     short loc_18000BBD4
0x18000bbc0  mov     rdx, [rbp+0B8h]
0x18000bbc7  mov     ecx, [rbp+48h]
0x18000bbca  call    _XcptFilter_0
0x18000bbcf  mov     [rbp+50h], eax
0x18000bbd2  jmp     short loc_18000BBDB
0x18000bbd4  mov     dword ptr [rbp+50h], 0
0x18000bbdb  mov     eax, [rbp+50h]
0x18000bbde  add     rsp, 20h
0x18000bbe2  pop     rbp
0x18000bbe3  retn
0x18000bbe5  push    rbp
0x18000bbe7  sub     rsp, 20h
0x18000bbeb  mov     rbp, rdx
0x18000bbee  mov     rax, [rcx]
0x18000bbf1  mov     edx, [rax]
0x18000bbf3  mov     [rbp+0C0h], rcx
0x18000bbfa  mov     [rbp+58h], edx
0x18000bbfd  mov     eax, [rbp+58h]
0x18000bc00  cmp     eax, 0E06D7363h
0x18000bc05  jnz     short loc_18000BC1B
0x18000bc07  mov     rdx, [rbp+0C0h]
0x18000bc0e  mov     ecx, [rbp+58h]
0x18000bc11  call    _XcptFilter_0
0x18000bc16  mov     [rbp+60h], eax
0x18000bc19  jmp     short loc_18000BC22
0x18000bc1b  mov     dword ptr [rbp+60h], 0
0x18000bc22  mov     eax, [rbp+60h]
0x18000bc25  add     rsp, 20h
0x18000bc29  pop     rbp
0x18000bc2a  retn
0x18000bc2c  push    rbp
0x18000bc2e  sub     rsp, 20h
0x18000bc32  mov     rbp, rdx
0x18000bc35  mov     rax, [rcx]
0x18000bc38  mov     edx, [rax]
0x18000bc3a  mov     [rbp+0C8h], rcx
0x18000bc41  mov     [rbp+68h], edx
0x18000bc44  mov     eax, [rbp+68h]
0x18000bc47  cmp     eax, 0E06D7363h
0x18000bc4c  jnz     short loc_18000BC62
0x18000bc4e  mov     rdx, [rbp+0C8h]
0x18000bc55  mov     ecx, [rbp+68h]
0x18000bc58  call    _XcptFilter_0
0x18000bc5d  mov     [rbp+70h], eax
0x18000bc60  jmp     short loc_18000BC69
0x18000bc62  mov     dword ptr [rbp+70h], 0
0x18000bc69  mov     eax, [rbp+70h]
0x18000bc6c  add     rsp, 20h
0x18000bc70  pop     rbp
0x18000bc71  retn
0x18000bc73  push    rbp
0x18000bc75  sub     rsp, 20h
0x18000bc79  mov     rbp, rdx
0x18000bc7c  mov     rax, [rcx]
0x18000bc7f  mov     edx, [rax]
0x18000bc81  mov     [rbp+0D0h], rcx
0x18000bc88  mov     [rbp+78h], edx
0x18000bc8b  mov     eax, [rbp+78h]
0x18000bc8e  cmp     eax, 0E06D7363h
0x18000bc93  jnz     short loc_18000BCAC
0x18000bc95  mov     rdx, [rbp+0D0h]
0x18000bc9c  mov     ecx, [rbp+78h]
0x18000bc9f  call    _XcptFilter_0
0x18000bca4  mov     [rbp+80h], eax
0x18000bcaa  jmp     short loc_18000BCB6
0x18000bcac  mov     dword ptr [rbp+80h], 0
0x18000bcb6  mov     eax, [rbp+80h]
0x18000bcbc  add     rsp, 20h
0x18000bcc0  pop     rbp
0x18000bcc1  retn
0x18000bcc3  push    rbp
0x18000bcc5  sub     rsp, 20h
0x18000bcc9  mov     rbp, rdx
0x18000bccc  mov     rax, [rcx]
0x18000bccf  mov     edx, [rax]
0x18000bcd1  mov     [rbp+0D8h], rcx
0x18000bcd8  mov     [rbp+88h], edx
0x18000bcde  mov     eax, [rbp+88h]
0x18000bce4  cmp     eax, 0E06D7363h
0x18000bce9  jnz     short loc_18000BD05
0x18000bceb  mov     rdx, [rbp+0D8h]
0x18000bcf2  mov     ecx, [rbp+88h]
0x18000bcf8  call    _XcptFilter_0
0x18000bcfd  mov     [rbp+90h], eax
0x18000bd03  jmp     short loc_18000BD0F
0x18000bd05  mov     dword ptr [rbp+90h], 0
0x18000bd0f  mov     eax, [rbp+90h]
0x18000bd15  add     rsp, 20h
0x18000bd19  pop     rbp
0x18000bd1a  retn
0x18000bd1c  push    rbp
0x18000bd1e  sub     rsp, 20h
0x18000bd22  mov     rbp, rdx
0x18000bd25  mov     rax, [rcx]
0x18000bd28  mov     edx, [rax]
0x18000bd2a  mov     [rbp+0E0h], rcx
0x18000bd31  mov     [rbp+98h], edx
0x18000bd37  mov     eax, [rbp+98h]
0x18000bd3d  cmp     eax, 0E06D7363h
0x18000bd42  jnz     short loc_18000BD5E
0x18000bd44  mov     rdx, [rbp+0E0h]
0x18000bd4b  mov     ecx, [rbp+98h]
0x18000bd51  call    _XcptFilter_0
0x18000bd56  mov     [rbp+0A0h], eax
0x18000bd5c  jmp     short loc_18000BD68
0x18000bd5e  mov     dword ptr [rbp+0A0h], 0
0x18000bd68  mov     eax, [rbp+0A0h]
0x18000bd6e  add     rsp, 20h
0x18000bd72  pop     rbp
0x18000bd73  retn
0x18000bd75  push    rbp
0x18000bd77  sub     rsp, 20h
0x18000bd7b  mov     rbp, rdx
0x18000bd7e  cmp     dword ptr [rbp+118h], 1
0x18000bd85  ja      short loc_18000BD91
0x18000bd87  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
